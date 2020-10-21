pipeline{
  properties([parameters([string(defaultValue: 'master', description: '', name: 'branch_name', trim: true)])])
  agent {
    label 'Med'
    }
  stages {
    stage ('git'){
     steps {
      git url: 'https://github.com/jayaprakash521/spc.git',branch: "${params.branch_name}"
      }
     }
    stage ('build the code'){
      steps {
       when branch_name == master
         sh 'mvn package'
       
      steps {
       sh 'mvn clean package'
       }
      
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
    
