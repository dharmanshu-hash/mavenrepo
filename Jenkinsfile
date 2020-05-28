pipeline {
agent { label 'devserver' }
stages {
stage('checkoutstage'){  
steps{
checkout([$class: 'GitSCM', 
    branches: [[name: '*/feat01']], 
    userRemoteConfigs: [[credentialsId: '8054212b-ad19-4d76-b931-387435cb2346', url: 'https://github.com/dharmanshu-hash/mavenrepo.git']]
])

     }
        }  

stage('buildstage'){ 
steps{
sh "mvn package"
     }
        }  
stage('tomcat'){
steps{
sh "scp /root/workspace/Pipeline-demo/target/studentapp-2.1.1-FEAT01-SNAPSHOT.war 3.82.215.95:/var/lib/tomcat/webapps"
sh "mkdir $BUILD_NUMBER"
}
     }
         
       }  
         } 
