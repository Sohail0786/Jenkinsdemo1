def a
pipeline{
	agent any
	
	stages{
		stage("Playbook"){
			steps {
				checkout ([$class: 'GitSCM'])
				userRemoteConfigs: [[
				url : 'https://github.com/Sohail0786/Jenkinsdemo1.git',
				]]
				}
		}
		stage ("Run playbook1"){
			steps	{
				sh ''' 
				mkdir -p tmp
				echo "ds1,ds2,ds3" > tmp/datasetname.txt
				a=$(cat tmp/datasetname.txt)
				echo $a
				echo "key="$a"" > tmp/datasetname.properties
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
