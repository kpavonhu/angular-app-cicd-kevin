pipeline {
   agent any

   environment {
       LISTA_CORREOS = 'kevinpavonucreativa@gmail.com'
       CUERPO_CORREO = "El pipeline ${BUILD_URL} tuvo un resultado"
       TITULO_CORREO = "${BUILD_URL} STATUS"
   }

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

   post {
       success {
          emailext body: "${CUERPO_CORREO} exitoso", subject: "${TITULO_CORREO}", to "${LISTA_CORREOS}"
       }
       failure {
          emailext body: "${CUERPO_CORREO} fallido", subject: "${TITULO_CORREO}", to "${LISTA_CORREOS}"
       }
       
   }
}