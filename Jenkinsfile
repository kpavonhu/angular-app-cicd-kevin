pipeline {
   agent any

   stages{
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
   }
}