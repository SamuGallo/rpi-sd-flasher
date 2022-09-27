# rpi-sd-flasher
rpi-sd-flasher è un software che permette di scrivere immagini per Raspberry pi 4 su schede micro SD.
il software è composto da un codice sorgente in C che esegue tramite un file eseguibile linux, uno script bash che tramite zenity esegue le operazioni e interagisce con l'utente tramite GUI

per aggiungere una voce al menù di scelta del sistema operativo:
1) aprie con qualsiasi editor il file rpi-sd-flasher.sh persente nella cartella /home/$USER/rpi-sd-flasher
2) individuare il commento (#scelta del sistema operativo) presente alla riga 12
3) alla riga 20 sarà presente una voce chiamata "scegli manualmente l'immagine"
4) copiare ed incollare la voce in una nuova riga sotto ad essa
5) modificare la voce appena creata rinominandola a piacimento
6) copiare negli appunti il nome appena assegnato
7) spostarsi alla riga 174
8) dupplicare l'ultima parte del costrutto elif sotto a quest'ultimo e modificare le voci:

echo "downloading file: filename" sostituendo la parte filename con il nome del file da scaricare

wget  -nc -c -P /home/$USER/rpi-sd-flasher/images URL sostituendo URL con l'URL del file da scaricare

dd if="/home/$USER/rpi-sd-flasher/images/filename sostituendo la parte filename con il nome del file scaricato in precedenza

rm /home/$USER/rpi-sd-flasher/images/filename, anche qui sostituendo la parte filename con il nome del file scaricato in precedenza

9) salvare il file
