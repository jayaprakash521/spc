node('Ubuntu') {
    parameters {
      choice(name: 'branch_name', choices: ['master','sprint-1','sprint-2'], description: 'Pick something')
      }
   stage('SCM') {
      // git clone
	  git 'https://github.com/jayaprakash521/spc.git'
   }
   
   stage ('build the packages') {
      // mvn package
	  if (params.branch_name == 'master') {
	       sh 'mvn package'
		   }
	  else {
	      sh 'mvn clean package'
		  }
   }

    stage ('archival') {
     // archiving artifacts
	   archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
   }

}
