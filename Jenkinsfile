pipeline {
    agent any

    stages {
        stage('Invoke Lambda Function') {
            steps {
                script {
                    // Replace with your function name and payload (if any)
                    sh 'aws lambda invoke --function-name Akshay_Python_Test --payload \'{"key1": "value1"}\' output.json'

                    // Optionally, process the output (if needed)
                    if (fileExists('output.json')) {
                        import groovy.json.JsonSlurper
                        def jsonSlurper = new JsonSlurper()
                        def jsonData = jsonSlurper.parse(file('output.json'))
                        // Access data from jsonData object
                        echo "Lambda function output: ${jsonData.key2}"
                    }
                }
            }
        }
    }
}

