# Gjestebok Database-implementasjon

Denne implementasjonen legger til persistent database-lagring for gjesteboken, slik at meldinger deles mellom alle brukere.

## Nåværende implementasjon (Mock)

Akkurat nå bruker systemet en mock-implementasjon som simulerer en delt database ved å bruke localStorage med ekstra funksjonalitet. Dette demonstrerer konseptet og fungerer som fallback.

## Produksjonsimplementasjon med Firebase

For ekte produksjonsbruk kan man enkelt bytte til Firebase Realtime Database:

### 1. Opprett Firebase-prosjekt

1. Gå til [Firebase Console](https://console.firebase.google.com/)
2. Opprett nytt prosjekt
3. Aktiver Realtime Database
4. Sett opp security rules (eksempel):

```json
{
  "rules": {
    "guestbook-messages": {
      ".read": true,
      ".write": true,
      "$messageId": {
        ".validate": "newData.hasChildren(['name', 'message', 'timestamp']) && newData.child('name').isString() && newData.child('message').isString() && newData.child('timestamp').isString()"
      }
    }
  }
}
```

### 2. Erstatt mock-implementasjonen

Bytt ut mock-scriptet i `gjestebok.html` med:

```html
<!-- Firebase SDK -->
<script type="module">
    import { initializeApp } from 'https://www.gstatic.com/firebasejs/10.7.1/firebase-app.js';
    import { getDatabase, ref, push, onValue, off } from 'https://www.gstatic.com/firebasejs/10.7.1/firebase-database.js';
    
    const firebaseConfig = {
        apiKey: "DIN_API_KEY",
        authDomain: "ditt-prosjekt.firebaseapp.com",
        databaseURL: "https://ditt-prosjekt-default-rtdb.europe-west1.firebasedatabase.app",
        projectId: "ditt-prosjekt",
        storageBucket: "ditt-prosjekt.appspot.com",
        messagingSenderId: "123456789",
        appId: "1:123456789:web:abc123"
    };
    
    window.firebaseApp = initializeApp(firebaseConfig);
    window.database = getDatabase(window.firebaseApp);
    window.firebaseRef = ref;
    window.firebasePush = push;
    window.firebaseOnValue = onValue;
    window.firebaseOff = off;
</script>
```

## Fordeler med denne implementasjonen

1. **Fallback-system**: Fungerer selv om database ikke er tilgjengelig
2. **Realtime oppdateringer**: Meldinger vises umiddelbart for alle brukere
3. **Enkel å vedlikeholde**: Minimal kode og avhengigheter
4. **Skalerbar**: Firebase håndterer skalering automatisk
5. **Gratis**: Firebase har generøs gratis tier

## Alternative løsninger

1. **Supabase**: Moderne alternativ til Firebase
2. **GitHub Gists API**: Bruke GitHub som database
3. **Netlify Forms**: For statisk form-håndtering
4. **JSON storage services**: Som JSONBin eller myjson

## Sikkerhet

- API-nøkler kan være offentlige for Firebase web-apps
- Sett opp passende database-regler for å forhindre spam
- Vurder rate limiting og input validation
- Legg til moderasjon for upassende innhold