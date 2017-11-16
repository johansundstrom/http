# HTTP
Kommunicera med HTTP
* Kommunikation sker genom _Requests_ som genererar ett _Response_
* Alla typer av data kan sändas med HTTP
* HTTP använder en klient-server model
* Senaste versionen av HTTP är "HTTP/1.1", föregångaren heter "HTTP/1.0"
* Det finns 8 st olika metoder av _Request's_ men fyra an vanligast förekommande
* Protokollet HTTP är ett felsäkert världsomspännande protokoll
* Återkoppling ges vid sändning
* Sändning sker i klartext
* 
## HTTP Metoder
* GET, POST, PUT, DELETE är de vanligaste metoderna

## HTTP GET Request
* En klient sänder ett request enligt följande...
```
1. En requestrad
2. Inga eller flera header fält följt av CRLF
3. En tom rad med endast CRLF (betyder slut på header)
4. Valfritt meddelandefält
```
