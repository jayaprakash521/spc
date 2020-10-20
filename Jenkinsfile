node('Med') {
     properties([parameters([string(defaultValue: 'master', description: '', name: 'branch_name', trim: false)])])
     stage('GIT') {
      git url: 'https://github.com/jayaprakash521/spc.git',branch: "${params.branch_name}"
      }
     stage('build') {
      if (branch_name == 'master') {
         sh 'mvn package'
	 }
      else {
         sh 'mvn clean package'
      }
     stage('archive artifacts') {
      archive 'target/*.jar'
      }
     stage('junit test results') {
      junit 'target/surefire-reports/*.xml'
      }
   }

