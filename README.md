# Tabellone della Tombola

### Usage

Apri il file `build/tombola.html` dal tuo browser preferito.  
Per pulire il tabellone fare click sul titolo (chiede conferma).  

### Rake

Il file HTML è costruito utilizzando le tecnologie HAML + Coffescript.  
Per generare il file eseguire il rake task hamlize (default).  

    $ rake  

Il task inoltre copia il file `background.jpg` nella cartella di destinazione build.

### Wallpaper

La pagina cercherà lo sfondo con il nome `background.jpg` nella cartella build.
