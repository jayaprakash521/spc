pipeline{
  agent {
    label 'Med'
    }
  parameters {
    choice(
        name: 'branch',
        choices: "master\nsprint-1",
        description: 'branch name' )
	}
  stages {
    stage ('git'){
     steps {
      git url: 'https://github.com/jayaprakash521/spc.git', branch: "${params.branch}"
      }
     }
    stage ('build the code'){
     when {
     expression {
       branch == 'master';
       }
      }
     steps {
      sh 'mvn clean package'
      }
     }
    
    stage ('archive'){
      steps {
       archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
       }
      }
    stage ('junit'){
      steps {
        junit 'target/surefire-reports/*.xml'
	}
      }
  }
}
    
