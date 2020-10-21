pipeline{
  agent {
    label 'Med'
    }
  stages {
    stage ('params') {
     steps { 
       script {
         properties([parameters([string(defaultValue: 'master', description: '', name: 'branch_name', trim: true)])])
	 }
	}
     }
    stage ('git'){
     steps {
      git url: 'https://github.com/jayaprakash521/spc.git',branch: "${params.branch_name}"
      }
     }
    stage ('build the code'){
      when branch_name == master
        steps {
         sh 'mvn package'
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
    
