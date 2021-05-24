def a
pipeline{
	agent any
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
