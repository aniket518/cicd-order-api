pipeline{
	agent any
	stages{
		stage('Build'){
			steps{
				echo 'building the application'
				bat 'mvn clean install'
			}
		}
		
		stage('Publishing'){
			steps{
				echo 'Publishing the artifact to exchange'
				bat 'mvn clean deploy -DskipTests'
			}
		}
		
		stage('Test'){
			steps{
				echo 'Testing munits - skipped the munit testing as no munits'
			}
		}
		
		stage('Deployment') {
           steps {
               echo 'Deploying the application to cloudhub2.0'
               bat 'mvn clean deploy -DmuleDeploy'
           }
       }
	}
}