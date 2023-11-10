pipeline {
  agent any
  stages {
      stage('Deleting existing repo')
           {
           steps {
              sh "rm -rf my-app2"
                 }
           }
         stage('Clone and Delete Repo')
           {
           steps {
              sh "git clone https://github.com/ahesmat/my-app2.git"
              sh "export PATH=$PATH:/var/lib/jenkins/apache-maven-3.9.5/bin"
              sh "/var/lib/jenkins/apache-maven-3.9.5/bin/mvn clean -f my-app2"
                 }
           }
            stage('Test')
           {
           steps {
              sh "/var/lib/jenkins/apache-maven-3.9.5/bin/mvn test -f my-app2"
                 }
           }
              stage('Deploy')
           {
           steps {
             sh  "/var/lib/jenkins/apache-maven-3.9.5/bin/mvn package -f my-app2"
                 }
           }


}
}