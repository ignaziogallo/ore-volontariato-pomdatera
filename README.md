# 🍎 Pom da Tera - Gestione Ore Volontariato

Un'applicazione web leggera e reattiva per la gestione delle ore di volontariato dell'associazione **Pom da Tera**. L'app permette ai soci di registrare le proprie attività tramite Google Auth e agli amministratori di supervisionare i dati e gestire l'anagrafica.

## 🚀 Funzionalità
* **Login Google**: Accesso sicuro senza password.
* **Registrazione Ore**: Form rapido per inserire attività, ore, data e descrizione.
* **Tabella Pivot**: Riepilogo automatico delle ore per socio e per tipologia di attività.
* **Diario di Bordo**: Visualizzazione dettagliata delle attività cliccando sul nome del socio.
* **Pannello Admin**: (Solo per utenti autorizzati) Eliminazione record e associazione nomi reali alle email.

---

## 🛠️ Guida per lo Sviluppo Locale (Linux)

Se vuoi modificare l'app o testare i comandi Firebase in locale sul tuo sistema Linux, segui questi passaggi.

### 1. Installazione Firebase Tools
Per prima cosa, installa Node.js (se non lo hai) e i tools di Firebase globalmente:

```bash
# Aggiorna i pacchetti (Debian/Ubuntu)
sudo apt update
sudo apt install nodejs npm

# Installa Firebase CLI
sudo npm install -g firebase-tools
```

### 2. Login e Inizializzazione
Spostati nella cartella del progetto e collega il tuo account Google:

```bash
# Accedi al tuo account Google
firebase login

# Inizializza il progetto (seleziona Hosting e Firestore se richiesti)
firebase init
```
Durante _firebase init_:
-    Scegli Hosting: Configure files for Firebase Hosting.
-    Seleziona il tuo progetto esistente pom-da-tera-....
-    Alla domanda sulla cartella pubblica, scrivi . (punto) se il tuo index.html è nella cartella principale.

### 3. Test in Locale
Per vedere le modifiche in tempo reale senza pubblicarle:

```bash
# Avvia un server locale
firebase serve
```
L'app sarà visibile su _http://localhost:5000_

## 📦 Deploy (Pubblicazione)
**Opzione A: Firebase Hosting (Consigliata)**

Se hai configurato Firebase Hosting, per rendere pubbliche le modifiche digita:
```bash
firebase deploy
```
**Opzione B: GitHub Pages (Alternativa rapida)**
Se preferisci usare GitHub Pages dopo aver pushato il codice:
*    Vai su Settings del repository.
*    Clicca su Pages.
*    Seleziona Branch: main e clicca Save.

## 📂 Struttura File
*    index.html: Contiene l'intera logica (HTML, CSS Tailwind, e JavaScript Firebase SDK 9).
*    README.md: Questa guida.

## 🔑 Configurazione Database (Firestore)
Assicurati che la collezione users contenga documenti dove l'ID è l'email del socio e sia presente il campo admin: true per abilitare i privilegi amministrativi.
_Sviluppato con ❤️ per Pom da Tera_.
