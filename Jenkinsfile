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
	
	parameters {

			extendedChoice(defaultValue: 'NA',
			description: 'Select DB name if your required DB is available. If your intended DB name is not available do not select any option and proceed to build to create your DB',
			multiSelectDelimiter: ',', 		
			name: 'DB_NAME',
			propertyFile: '/var/lib/jenkins/workspace/Jenkinsfiletest3/tmp/datasetname.properties',
			propertyKey: 'key',
			quoteValue: false,
			saveJSONParameterToFile: false, 
			type: 'PT_SINGLE_SELECT', visibleItemCount: 10)
    }
	stages {
		stage('Check if DB exist'){
			steps {
				script {
					if ( params.DB_NAME.contains('NA')) {
					echo "Your intended Database does not exist. Please click on the proceed option to start creation of the new Database."
					echo "skipped"
				}
			}
		}
			post { 
		        success { 
				
				script{
					if( params.DB_NAME.contains('NA') ){
	   
					emailext body: "Job_name: ${env.JOB_NAME} Build_number: ${env.BUILD_NUMBER}\n The Database name does not exist hence please click on this link to approve the Database creation process : ${env.BUILD_URL}/console", 
				recipientProviders: [[$class: 'DevelopersRecipientProvider']], 
				subject: '$PROJECT_NAME - Build # $BUILD_NUMBER - Approve Request for New Database Creation!', 
				to: sohail0786@hotmail.co.uk" 
		  
      }
		  
    }
		        
		        }
		   }
    }
		stage('Create DB if not exist'){
			steps {	
				script {
					if ( params.DB_NAME.contains('NA')) {
					input message: "Proceed or Abort"
					// input message: "Proceed or Abort", submitter: "username", parameters: [string(name:'username', defaultValue: 'user1', description: 'Username of the user pressing Ok')] 
					echo "Attach your DB creation script in the script block here, which will be executed post approval"
					}
					else {
					echo "skipped"
		   }
		 }  
		}
	 }
	 
		stage('Run play for existing DB'){
		steps{
				script {
			if ( "$DB_NAME" != "NA" ) {
		 
		 
		 
				 }
			 }
		 }
	 }
	 
	 	
}
