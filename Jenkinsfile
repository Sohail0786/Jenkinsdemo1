pipeline {
    agent any
	Stages {
		stage('Example'){
			input{
			message "Select the DB"
			OK 'Proceed'
			parameters {
			extendedChoice defaultValue: 'test_db1,test_db2,test_db3,test_db4',
			description: '',
			descriptionPropertValue: 'test_db1,test_db2,test_db3,test_db4',
			multiSelectDelimiter: ',', 		
			name: 'DB_NAME',
			quoteValue: false,
			saveJSONParameterToFile: false,
			type: 'PT_SINGLE_SELECT', 
			value: 'test_db1,test_db2,test_db3,test_db4',
			visibleItemCount: 5)
            }
        }
    }
            steps {
            echo "DB selected by you is ${DB_NAME}"
            }

    }

	
}
