node('Ubuntu') {
   properties([parameters([choice(choices: ['master', 'sprint-1', 'sprint-2'], description: '', name: 'Branch_name')])])1
   stage('SCM') {
      // git clone
	  git 'https://github.com/jayaprakash521/spc.git'
   }
   
   stage ('build the packages') {
      // mvn package
	  if env.branch == 'master'
	       sh 'mvn package'
	  else
	      sh 'mvn clean package'
   }

    stage ('archival') {
     // archiving artifacts
	   archiveArtifacts artifacts: 'webapp/target/*.war', followSymlinks: false
   }

}
