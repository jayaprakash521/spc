pipeline {
     agent {
        label 'Ubuntu'
       }
     stages {
        stage('git clone') {
            steps {
               git 'https://github.com/jayaprakash521/spc.git'
             }
         }
        stage('build') {
            steps {
               sh 'mvn clean package'
            }
          }
        stage('archeve') {
            steps {
              archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
              }
          }
        stage('junit') {
            steps {
              junit 'target/surefire-reports/*.xml'
	      }
	  }
     }
}
           
