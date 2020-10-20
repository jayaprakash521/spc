node('Med') {
     stage('GIT') {
      git 'https://github.com/jayaprakash521/spc.git'
      }
     stage('build') {
      sh 'mvn package'
      }
     stage('archive artifacts') {
      archive 'target/*.jar'
      }
     stage('junit test results') {
      junit 'target/surefire-reports/*.xml'
      }
   }
