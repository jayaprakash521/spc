node('Ubuntu') {
   properties([parameters([choice(choices: ['master', 'feature-1', 'feature-2'], description: '', name: 'Branch_name')])])
   stage('SCM') {
      // git clone
	  git url: 'https://github.com/jayaprakash521/spc.git',branch: "${params.Branch_name}"
   }
   
   stage ('build the packages') {
      // mvn package
	  sh 'mvn clean package'
   }

   
   
   stage ('archival') {
     // archiving artifacts
	 archive 'target/*.jar'
   }

}        
