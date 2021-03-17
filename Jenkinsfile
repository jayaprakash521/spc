pipeline {
     agent {
        label 'Jaya'
       }
     stages {
        stage('git clone') {
            steps {
               git https://github.com/jayaprakash521/spc.git
             }
         }
        stage('build') {
            steps {
               sh 'mvn clean package'
            }
          }
        stage('archeve') {
            steps {
              archive 'target/*.jar'
              }
          }
        stage('junit') {
            steps {
              junit 'target/surefire-reports/*.xml'
	      }
	  }
     }
}
           
