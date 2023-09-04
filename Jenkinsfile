pipeline{
    tools{
        maven 'mymaven'
    }
	agent any
      stages{
           stage('Checkout the code'){
               steps{
		        echo 'cloning the repo'
                 	git 'https://github.com/prakrishna2004/DevOpsDemo.git'
              }
          }
          stage('Package the code'){
             
              steps{
                  echo 'Packaging the code..'
                  sh 'mvn package'
	      }
          }
          stage('Copy war file to current directory'){		  
              steps{ 
		        echo 'Copy ware file to current directory'
                  	sh 'cp /var/lib/jenkins/workspace/CICDPipeline/target/addressbook.war .'
              }
          }
	stage('Build docker image'){
             
              steps{
                  echo 'Building docker image'
                  sh 'docker build -t myimage .'
	      }
          }
      }
}
