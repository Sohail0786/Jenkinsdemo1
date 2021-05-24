def a
pipeline{
	agent any
	
	stages{
		stage("Playbook"){
			steps {
				checkout ([$class: 'GitSCM'])
				branches: [[name:'*./ branchname-1']],
				extensions: scm.extensions,
				userRemoteConfigs: [[
				url : ' https://github.com/Sohail0786/jenkinsdemo1/blob/main/jenkinsfile',
				]]
				
					cat /tmp/dsources
					sh '''
				}
			}
	}
		stage ("Run playbook1")
			steps	{
				sh ''' 
				ansible-playbook -i ./host delphix-dsources.yml -vvvv
				'''
		
		}
	}
		stage ("Read dsources file"){
			steps	{
				sh"""
				cat /tmp/dsources
				a= 'cat /tmp/dsources'
				echo $a
				"""
				}
		}
	}
