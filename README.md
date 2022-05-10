# Simonyc
Il mio primo quadrante per il fitbit ionic.
La particolarità di questo quadrante è che ha una immagine di background facilmente modificabile, mostra l'orologio, la data, la carica, i passi e la frequenza cardiaca.

# Utilizzo
Andate su https://studio.fitbit.com/ e loggatevi col vostro account, accettate la licenza per sviluppatori del fitibit.
Adesso andate nelle impostazioni dell'app fitbit sul cellulare, andate più precisamente nelle impostazioni dell'orologio e comparirà una nuova voce: menù svuluppatore: andate in quella voce e mettete la spunta su "Bridge per sviluppatori", poi sincronizzate l'orologio.

Dopo aver connesso l'orologio alla rete wifi su cui si trovano cellulare e computer, andate nelle impostazioni dell'orologio, ed attivate il "Developer Bridge". Deve dirvi "connected to server".

Andate in fitbit studio e create un nuovo progetto, a questo punto potete usare il drag and drop per portare i files del progetto dentro il fitbit studio.
Se tutto è andato bene, dovete cliccare su "Select a phone, select a device" e dovrebbero comparirvi proprio il vostro cellulare ed il vostro dipsositivo, selezionateli entrambi.

Adesso dovete aprire il file "Package.json" e selezionare il tipo del vostro dispositivo, possibilmente a partire da "sdk version" 5.0 a scendere, finché non lo trovate.
Assicuratevi anche che "Activity" e "Heart rate" "requested permissions" siano attive.

A questo punto, se tutti e due i dispositivi sono collegati, è sufficiente andare su "run" per inviare il quadrante all'orologio.

# Bug noti
Pare che la batteria duri poco con questo quadrante, non so se è colpa del refresh rate molto alto o se è colpa del developer bridge.
L'immagine di sfondo è bruttina, ma vuole essere un proof of concept.
Il sistema è tarato per il fitibit ionic che ha uno schermo di 300x300, se si vuole adattarlo al versa, bisogna ridimensionare il file resources/index.gui, responsabile dell'svg dell'interfaccia.

# Cambiare immagine di sfondo
Per cambiare l'immagine di sfondo, è sufficiente creare una immagine di 300x300 pixels, chiamarla "background.png" ed importarla nella cartella "resources", andando a sovrascrivere l'attuale.

# Cambiare refresh rate
L'ultima riga di index.js è la seguente:
setInterval(work, 1000);

1000 è il numero di millisecondi per il refresh rate delle informazioni del quadrante, ossia 1 secondo.
Cambiare il numero a proprio piacimento.
