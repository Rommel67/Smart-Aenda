# La Mia Agenda — V2 personalizzata

Versione personale Android con reminder reali, richiami, musica/locali, attività Agenti IA e impostazioni audio.

## Novità V2

- Esito contatto con `Demo inviata` e `Da richiamare`.
- Quando scegli `Da richiamare`, data e ora diventano obbligatorie e viene creato un reminder collegato al contatto.
- I richiami attivi hanno indicatore rosso sia sul contatto sia nei Reminder.
- Reminder Android programmati con `allowWhileIdle`, quindi pensati per funzionare anche con schermo spento/app chiusa, se i permessi Android sono concessi.
- Sezione `Agenti IA` separata per test, demo, follow-up, richiami e prossima azione.
- Sezione `Impostazioni` con 4 suonerie: Classica, Digitale, Soft, Urgente.
- Modalità: suoneria + vibrazione / solo suoneria / solo vibrazione.
- Prova suoneria, test notifica tra 10 secondi, controllo permessi.
- Suono breve all'apertura app (disattivabile).
- Backup include anche i dati Agenti IA e le impostazioni.

## Build GitHub

Workflow già predisposto in `.github/workflows/build-apk.yml`:
- Node 22
- Java 21
- `npm install`
- `npx cap sync android`
- `./gradlew assembleDebug`

L'APK viene caricato come artifact `agenda-apk`.

## IMPORTANTE — prima installazione V2

La V1 installata in precedenza era un APK debug generato da un runner GitHub diverso e può avere una firma differente.
Per installare questa V2 potrebbe essere necessario disinstallare UNA VOLTA la V1.

Da questa V2 in poi il progetto contiene una chiave di sviluppo stabile (`agenda-dev.keystore`) per mantenere la stessa firma nelle future build personali. Questa chiave NON è destinata alla pubblicazione su Google Play: per il Play Store andrà creata una chiave release separata e custodita in modo sicuro.

## Test consigliato dopo installazione

1. Apri `Impostazioni` e scegli una suoneria.
2. Premi `Prova suoneria`.
3. Premi `Controlla / attiva permessi`.
4. Premi `Test notifica tra 10 secondi`, blocca lo schermo e verifica suono/vibrazione.
5. Crea un contatto Musica/Locali con esito `Da richiamare`, data e ora a pochi minuti di distanza.
6. Verifica badge rosso, comparsa nei Reminder e notifica a schermo spento.
