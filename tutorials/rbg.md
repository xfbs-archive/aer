# RBG Zugang

Da Bluespec leider nur im RBG-Pool installiert ist, muss man, zum Experimentieren, den Compiler auf den Rechnern des RBG-Pools nutzen. Das kann man aber auch sehr leicht von Zuhause aus, wenn man Zugang zum Pool hat. Das ist zum Glück leicht zu realisieren.

## SSH-Key generieren

    $ ssh-keygen

## SSH-Key hochladen

Im [RBG Accountmanagement](https://support.rbg.informatik.tu-darmstadt.de) kann man sich mit seiner TU-ID anmelden, und kann dort einen Account beantragen oder einen SSH-Key hochladen.

![RBG Account](rbgaccount.png)

Wenn man auf *SSH Public-Key registrieren* drückt, bekommt man eine Meldung, dass man in Kürze eine Mail mit weiteren Anweisungen bekommt. 

![RBG Email Nachricht](rbgsuccess.png)

Diese Mail enthält einen Link, auf den man gehen muss.

![RBG Email](rbgmail.png)

Wie man sieht, ist das Encoding von der Email nicht ganz korrekt. Ich gehe mal stark davon aus, dass die netten Leute vom RBG ein falsches Encoding angegeben haben. Zum Glück können wir das leicht herausfinden!

Wir schauen uns die Email also näher an. Die Header sind für uns in diesem Fall nicht interessant. Die Email ist eine MIME-Multipart Nachricht, aber in beiden (Text und HTML) ist das Encoding gleichermaßen falsch. Schauen wir uns doch den HTML-Teil an.

>   Content-Type: text/html; charset="utf-8"
>   Content-Disposition: inline
>   Content-Transfer-Encoding: quoted-printable
>   
>   
>   &lt;p&gt;
>     Sehr geehrte/r Informatik Student,
>     <br/>
>     F=FCr Ihren RBG-Account wurde ein SSH-Key-Update =FCber den Self-Support =
>     angefordert,
>     der noch best=E4tigt werden muss.
>   &lt;/p&gt;

Was ist hier der Fehler? Wir sehen, dass als Charset UTF-8 angegeben wurde. Das ist schonmal sehr gut, denn UTF-8 kann deutsche Sonderzeichen Repräsentieren (und ein paar Millionen andere Zeichen). Das Transfer-Encoding wurde als *quoted-printable* angegeben. Das bedeutet, dass alles, was nicht ASCII ist als `=FF` encoded wird, wobei `FF` die Hexadezimale Darstellung des Zeichens ist. 

Wir können also sehen, dass hier ein `ü` als `0xFC` encoded wurde, und ein `ä` als `0xE4`. Aber Moment, das ist doch nicht UTF-8! Mein Verdacht verstärkt sich, dass hier ein Windows-User herumgepfuscht hat. Windows nutzt nämlich für deutschen Text das [Windows-1250](https://en.wikipedia.org/wiki/Windows-1250) Encoding.

| Buchstabe (in Mail) | UTF-8 | Windows 1250 |
| --------- | ----- | ------------ |
| `ü` (`=FC`) | `C3 BC` | `FC` |
| `ä` (`=E4`) | `C3 A4` | `E4` |

Wenn man sich die Tabelle ansieht, erkennt man, dass hier ein falsches Encoding verwendet wurde (bzw. ein Encoding falsch angegeben wurde). Fail! Ich glaube, da muss der RBG nochmal dran.

## Per SSH einloggen

Hat man alles richtig gemacht, kann man sich nun per SSH einloggen.

[![asciicast](https://asciinema.org/a/4LZPxrkGcO7pYXHsdZpkaVw9I.png)](https://asciinema.org/a/4LZPxrkGcO7pYXHsdZpkaVw9I)
