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
   - Ingrese al repositorio. Luego ingrese a *Settings > Webhooks > Add webhook*.
   - En la opciòn *Payload URL* pegue el link que le entrega ngrok. Importante que ese link lo finalice agregando */github-webhook/*.
   - (https://postimg.cc/XrGMjhhY) 
   - Seleccione la opciòn *Let me select individual events* y asegurese de dejar seleccionada las opciones *Pull requests* y *Pushes*.
   - Posterior cree el Webhook. 

5. *Configuración del pipeline en Jenkins*
   - Primero instale el plugin de *Nodejs* y configurelo en las tools globales de Jenkins.
   - (https://postimg.cc/TpHMXGts)
   - Cree el pipeline y asegurese de dejar seleccionada la opciòn *GitHub hook trigger for GITScm polling*, esta opcion permite que Jenkins este atento al estado del repositorio que contiene el projecto, una vez detecte uun cambio ejecuta el pipeline. Permitiendo de esta manera la integraciòn continua.
   - (https://postimg.cc/jCcYZyPt)
   - Configure el repositorio que contiene el proyecto.
   - (https://postimg.cc/BXv9ytBD)


### Verificación del Funcionamiento:

- Al realizar cambios en el proyecto y estos sincronizarlos en el repositorio, genera que el pipeline se ejecuta en automatico.
- Evidencia de build: (https://postimg.cc/YvZHQkgF) 
  

## Diagrama de Alto Nivel de la preparación del CI/CD
---
![Diagrama_AltoNivel(1)](https://github.com/jamintonmoreno/nodejs-helloworld-api/assets/74082502/ad69046b-37fd-4d0e-a87e-073908ac3309)

