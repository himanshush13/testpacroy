pipeline {
   agent any
   stages{
         stage('ABAP Unit Test'){
               steps{
                     withCredentials([[$class: 'UsernamePasswordMultiBinding', credentialsId: 'NPL', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD']]) {
                     sh '''
                     newman run https://github.com/testabapdevops/pacroypipeline/blob/master/abap_unit_coverage.postman_collection.json -k --bail --environment https://github.com/testabapdevops/pacroypipeline/blob/master/NPL.postman_environment.json -k --timeout-request 120000 --global-var "username=$USERNAME" --global-var "password=$PASSWORD" --global-var "package=$zdevops"
                     '''
                     }
                }
         }    
   }
}
