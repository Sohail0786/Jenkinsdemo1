def a
pipeline{
	agent any
	
	stages{
		stage("checkout"){
			steps {
				checkout scm
		}
		stage ("Run playbook1"){
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
