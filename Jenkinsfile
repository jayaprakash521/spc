pipeline{
  agent {
    label 'Med'
    }
  stages {
    stage ('git'){
     steps {
      git 'https://github.com/jayaprakash521/spc.git'
      }
     }
    stage ('build the code'){
      steps {
       sh 'mvn package'
       }
      }
    stage ('archive'){
      steps {
       archiveArtifacts archive: 'target/*.jar'
       }
      }
    stage ('junit'){
      steps {
        junit 'target/surefire-reports/*.xml'
	}
      }
  }
}
    
