node('Jaya') {
   properties([parameters([choice(choices: ['master', 'feature-1', 'feature-2'], description: '', name: 'Branch_name')])])
   stage('SCM') {
      // git clone
         git 'https://github.com/jayaprakash521/spc.git'
   }
   
   stage ('build the packages') {
      // mvn package
	  sh 'mvn package'
   }

   
   
   stage ('archival') {
     // archiving artifacts
	 archive 'target/*.jar'
   }

}
