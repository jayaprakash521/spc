pipeline {
     agent {
        label 'Ubuntu'
       }
     parameters {
      choice(name: 'branch_name', choices: ['master','sprint-1','sprint-2'], description: 'Pick something')
      }
     stages {
        stage('git clone') {
            steps {
                git url: 'https://github.com/jayaprakash521/spc.git',branch: "${params.branch_name}"
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
               
