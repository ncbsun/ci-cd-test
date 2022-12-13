pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                script {
                def userInput = input(
                 id: 'userInput', message: 'Enter path of test reports:?', 
                 parameters: [
                 [$class: 'TextParameterDefinition', defaultValue: 'None', description: 'Path of config file', name: 'Config'],
                 [$class: 'TextParameterDefinition', defaultValue: 'None', description: 'Test Info file', name: 'Test']
                ])
                echo ("IQA Sheet Path: "+userInput['Config'])
                echo ("Test Info file path: "+userInput['Test'])
                              
                }
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                def userInput = input(
                            id: 'userInput', message: 'Enter path of test reports:?',
                            parameters: [

                                    string(defaultValue: 'None',
                                            description: 'Path of config file',
                                            name: 'Config'),
                                    string(defaultValue: 'None',
                                            description: 'Test Info file',
                                            name: 'Test'),
                ])
                // Save to variables. Default to empty string if not found.
                inputConfig = userInput.Config?:''
                inputTest = userInput.Test?:''

                // Echo to console
                echo("IQA Sheet Path: ${inputConfig}")
                echo("Test Info file path: ${inputTest}")
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}