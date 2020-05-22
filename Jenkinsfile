pipeline {
     agent any
     stages {
          stage("Compile") {
              steps {
                  sh "mvn compile"
              }
          }
          stage("Unit test") {
              steps {
                  sh "mvn test"
              }
          }
          stage("Code coverage") {
               steps {
                    sh "mvn jacoco:report"
                    publishHTML (target: [
                                   reportDir: 'target/site/jacoco',
                                   reportFiles: 'index.html',
                                   reportName: "JaCoCo Report"
                              ])
                    sh "mvn verify"
               }
          }
     }
}