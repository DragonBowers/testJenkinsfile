pipeline {
  agent {
    label 'java'
  }
   stages {
      stage('GetCode') {
         steps {
            git 'https://github.com/DragonBowers/spring3-mvc-maven-xml-hello-world.git'
         }
      }
      stage('Build') {
         steps {
            sh '/usr/local/mymaven/apache-maven-3.6.3/bin/mvn clean'
            sh '/usr/local/mymaven/apache-maven-3.6.3/bin/mvn package -Dmaven.skip.test=true'
         }
      }
      stage('Deploy') {
         steps {
            deploy adapters: [tomcat8(credentialsId: 'tomcat_admin', path: '', url: 'http://192.168.81.128:8080')], contextPath: null, war: 'target/spring3-mvc-maven-xml-hello-world-1.0-SNAPSHOT.war'
         }
      }
   }
}