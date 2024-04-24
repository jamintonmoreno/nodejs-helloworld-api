# NodeJs, helloworld API for test propouses.

This is a simple API that returns a welcome message.

## Run your local environment

### Clone the repository
```bash
git clone https://github.com/edgaregonzalez/nodejs-helloworld-api.git
```

### Install dependencies
```bash
npm install
```

### Run the tests
```bash
npm test
```

### Start the server
```bash
npm start
```

### Make a request
```bash
curl http://localhost:3000
```
# *CI/CD*
---
## Configuraciòn de Jenkins con ngrok:

1. *Instalación de ngrok:*
   - Instala ngrok desde la documentaciòn oficial. [página oficial](https://ngrok.com/download).
   - Sigue las instrucciones de instalación para tu sistema operativo.

2. *Exponer Jenkins usando ngrok:*
   - En la terminal de su pc o VM ejecute el siguiente comando:
   ```bash  
     ngrok http http://localhost:8080
   ```  
   - Una vez ejecutado este comando se iniciara el servicio de ngrok. En la opcion *Forwanding* se encuentra la URL en la cual esta desplegada la pagina. *Importante*, cuando cierre la terminal y vuelva a ejecutar el comando anterior la URL va a cambiar por lo tanto tendra que actualizar la informaciòn.
     -(https://postimg.cc/GH3dCXd4)

3. *Acceder a Jenkins a través de ngrok:*
   - Puedes dar click al enlace mencionado esto te llevara a la pagina, si presenta error.
   - Abre el navegador web y pega el enlace proporcionado por ngrok.
   - Una vez abra el enlace dar click en la opcion *Visit site*
   - (https://postimg.cc/9DSZqxpM)
   - Esto lo llevara a la pagina de inicio de Jenkins. Ingrese su usuario y contraseña.
   - (https://postimg.cc/BX7MMBpW)
     
4. *Configuración del webhook en el repositorio de GitHub:*
   - Ingrese al repositorio. Luego ingrese a *Settings > Webhooks > Cre* En la configuración de tu repositorio en GitHub, agrega una nueva URL de webhook apuntando al enlace de ngrok para los eventos "push" y "pull request".
   - Configurar webhook en GitHub (https://postimg.cc/WdNs30F4) 
   - Seleccionar eventos en GitHub (https://postimg.cc/V5d8sN3P) 

5. *Configuración de Jenkins para recibir notificaciones de GitHub:*
   - En Jenkins, configura un nuevo pipeline o proyecto y agrega las credenciales de GitHub.
     - Asegúrate de agregar la URL del repositorio de GitHub.
     - (https://postimg.cc/CBbbb02h) 
   - Activar la opción "GitHub hook trigger for GITScm polling" en Jenkins para que se accione como un gatillo que activa la construcción automática del proyecto cuando se produce un cambio en el repositorio de GitHub
     -(https://postimg.cc/rKxHD9DL)

6. *¡Preparado para recibir commits!*
   - En este punto, Jenkins responderá automáticamente a los commits en tu repositorio.
   - (https://postimg.cc/47X9JWkx) 

### Verificación del Funcionamiento:

- Para verificar su funcionamiento y completar la documentación de este README, se realizaron múltiples cambios en la rama principal, que fueron recibidos exitosamente por el proceso de Entrega Continua (CD).
  - Proceso finalizado de buil: (https://postimg.cc/239N735H) 
  - Logs que muestra que se lanzao la tarea (https://postimg.cc/rRL31YsL) 

## Diagrama de Alto Nivel de la preparación del CI/CD
---
![Diagrama_AltoNivel(1)](https://github.com/jamintonmoreno/nodejs-helloworld-api/assets/74082502/ad69046b-37fd-4d0e-a87e-073908ac3309)

