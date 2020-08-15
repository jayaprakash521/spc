pipeline {
  agent {
    label 'ubuntu-1'
  }
  stages {
    stage('git') {
       step {
         git 'https://github.com/jayaprakash521/spc.git'
       }
    }
    stage('build') {
       step {
         sh 'mvn clean package'
       }
    }
    stage('archive) {
       step {
         archieve 'target/*.jar'
       }
    }
  }
}
