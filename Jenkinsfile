pipeline{

agent {
  label 'LinuxBuildSlave1'
}


tools {
 maven 'Maven'
 jdk 'JAVA8'
}

stages{
          stage('get the code from GIT'){
                 steps {
                     git changelog: false, credentialsId: '1ce408e1-d630-4fa6-908f-952cef45ccae', poll: false, url: 'https://github.com/sampathgoparaju/webapp.git'

                       }
               }
          stage('build the source code'){
                 steps{
	   
	             sh 'mvn clean install'
		
                         }
                }

	  stage('send the mail'){
		steps{
                    emailext body: 'hi', subject: 'hi', to: 'sampathgoparaju@gmail.com'	 
		     }
                }
     
}
}
