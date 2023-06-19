pipeline {
   agent any

   stages{
       //Integracion Continua
       stage('Instalar Dependencias'){
           steps{
              sh 'npm install'
           }
       }
       
       stage('Compilacion del APP'){
           steps{
              sh 'npm run build'
           }
       }

       stage('Mostrar Archivos'){
           steps{
              sh 'ls -la'
           }
       }

       //Despliegue de la aplicacion
       stage('Despliegue de la aplicacion'){
           steps{
              sh 'cp dist/democlase06/* /tmp/deploy'
           }
       }
   }
}