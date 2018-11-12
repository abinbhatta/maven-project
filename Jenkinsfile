import groovy.json.*
pipeline {
    agent any
    stages {
        stage('Init') {
            steps {
                echo "testing"
            } 
        }
		stage('Build') {
            steps {
                echo "Building.."
				sh 'MVN clean package'
            } 
        }
		stage('Deploy') {
            steps {
                echo "Deploying.."
                timeout(time:5, unit:'DAYS'){
                    input message:'Approve Deployment'
                }
            } 
        }

    }
}        
