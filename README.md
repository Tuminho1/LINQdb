# LINQdb
1) Creare una una cartella nominandola in questo modo:
##### cognome.nome.4h.LINQdb (che in questo caso è il nome del progetto)
![image](https://user-images.githubusercontent.com/116791499/236146737-21c43785-a7f9-4943-a67b-0a5d2698cfd1.png)
__________________________________________________________________________________________________
2) Lanciare Visual Code e aprire la cartella appena creata
__________________________________________________________________________________________________
3) Lanciare un terminale su Visual Code utilizzando il seguente comando:

``` 
dotnet new console 
```
__________________________________________________________________________________________________
4) #### Qui invece troviamo il link con collegameto al download per scaricare il database di prova che si troverà nella sezione Download SQLite sample database

https://www.sqlitetutorial.net/sqlite-sample-database/
__________________________________________________________________________________________________
5) Una volta scaricato spostarlo nella cartella creata a inizio progetto e riaprire Visual Code nella pagina aperta in precedenza
__________________________________________________________________________________________________
6) Installare il plugin per Visual Code di nome SQLite, immagine qui sotto:
![image](https://user-images.githubusercontent.com/116791499/236141827-0368fb33-3d6b-414f-acba-8a4cefb9d43e.png)
__________________________________________________________________________________________________
7) Per aggiungere il plugin su Code bisogna fare pulsante destro su chinook.db (mentre si è su Visual Code) e cliccare "Open Databse", subito dopo entriamo nel csproj e cerchiamo `<PackageReference Include="sqlite-net-pc1" Version="1.8.116"`.
Se non funziona questo metodo utilizzare questo comando inserendolo nel terminale:
```
dotnet add package sqlite-net-pcl
``` 
__________________________________________________________________________________________________
8) Copiare questo codice nel proprio programma, scrivere `dotnet run` per vedere se funziona:
```
using SQLite;

//Connessione al Database

SQLiteConnection cn1 = new SQLiteConnection("chinook.db");

//Richieste al Database

var tblArtists = cn1.Query<Artist>("select * from artists");

//Stampa su console di quanti record sono presenti in tblArtists

Console.WriteLine($"In questa tabella ci sono {tblArtists.Count} record!");

//Classe di contenimento dei dati

public class Artist

{

    public int ArtistId{get;set;}
    public string Name{get;set;}
    
}
```
__________________________________________________________________________________________________
