# HTTP
Kommunicera med HTTP
* Kommunikation sker genom _Requests_ som genererar ett _Response_
* Alla typer av data kan sändas med HTTP
* HTTP använder en klient-server model
* Senaste versionen av HTTP är "HTTP/1.1", föregångaren heter "HTTP/1.0"
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

| Metod  | CRUD | Beskrivning   |
|--------|------|---------------|
| POST   | C    | Skickar data  |
| GET    | R    | Hämtar data   |
| PUT    | U    | Ersätter data |
| DELETE | D    | Raderar data  |

## HTTP GET Request

Ovanstående kan exempliferas med följande som begär filen /api/index.html från be9.asuscomm.com
```
GET /api/index.html HTTP/1.1<crlf>
Host: be9.asuscomm.com<crlf>
Accept-Language: sv-se<crlf>
Connection: Keep-Alive<crlf>
<crlf>
temp=21.123&date=1510834647&room=hall
```
Ett Javascript kan se ut på följande sätt (stackoverflow.com)
```javascript
var request = new XMLHttpRequest();
request.onreadystatechange = function() {
    if (request.readyState === 4) {
        if (request.status === 200) {
            document.body.className = 'ok';
            console.log(request.responseText);
        } else {
            document.body.className = 'error';
        }
    }
};
let url = "be9.asuscomm.com";
request.open("GET", url , true);
request.send(null);
```
