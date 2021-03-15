node {

   stage('SCM') {
      // git clone
	  git 'https://github.com/jayaprakash521/spc.git'
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
