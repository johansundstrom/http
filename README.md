# HTTP
Kommunicera med HTTP
* Kommunikation sker genom _Requests_ som genererar ett _Response_
* Alla typer av data kan sändas med HTTP
* HTTP använder en klient-server model
* Senaste versionen av HTTP är "HTTP/1.1", föregångaren heter "HTTP/1.0"
* HTTP/1.1 klarar t.ex. flera transaktioner på samma uppkoppling (snabbare)
* Det finns 8 st olika metoder av _Request's_ men de fyra vanligaste beskrivs här
* Protokollet HTTP är ett felsäkert världsomspännande protokoll
* Återkoppling ges vid sändning
* Sändning sker i klartext
* Radframmatningarna <crlf> är 0x0d, 0x0a, aka "\r\n"
* En klient sänder ett request enligt följande...
```
1. En requestrad
2. Inga eller flera header fält följt av CRLF
3. En tom rad med endast CRLF (betyder slut på header)
4. Valfritt meddelandefält
```

## HTTP Metoder
* GET, POST, PUT, DELETE är de vanligaste metoderna

| Metod  | CRUD | Beskrivning          | Användning                       |
|--------|------|----------------------|----------------------------------|
| POST   | C    | Skickar data         | namn/värde i postformat          |
| GET    | R    | Hämtar data          | namn/värde tillagd synlig på URL | 
| PUT    | U    | Ersätter/skapar data | namn/värde i postformat
| DELETE | D    | Raderar data         |

## HTTP GET Request

Ovanstående kan exempliferas med följande som begär filen /api/index.html från be9.asuscomm.com. 
```
GET /api/index.html HTTP/1.1<crlf>
Host: be9.asuscomm.com<crlf>
Accept-Language: sv-se<crlf>
Connection: Keep-Alive<crlf>
<crlf>
temp=21.123&date=1510834647&room=hall
```

## HTTP POST Request
```
POST /api HTTP/1.1<crlf>        //inget filnamn är begärt
Host: be9.asuscomm.com<crlf>
Content-Type: application/x-www-form-urlencoded<crlf>
Content-Length: 34<crlf>
<crlf>
temp=21.123&date=1510834647&room=hall
```

## HTTP PUT Request
* PUT Request ersätter befintlig data. Om inte detta existerar så skapas det istället, precis som POST
* Exempel 
```
PUT /api/room/ HTTP/1.1<crlf>         //inget filnamn är begärt
Host: be9.asuscomm.com<crlf>
Accept: application/json<crlf>
Content-Length: 37<crlf>
<crlf>
{
    "_Id": 4, 
    "room": "hall"
}
```

## HTTP DELETE Request
* PUT Request raderar befintlig data
* Exempel 
```
DELETE /api/room/ HTTP/1.1<crlf>         //inget filnamn är begärt
Host: be9.asuscomm.com<crlf>
Accept: application/json<crlf>
Content-Length: 17<crlf>
<crlf>
{
    "_Id": 4
}
```
