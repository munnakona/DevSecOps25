pipeline {
    agent any
      parameters{
        string (name: 'Branch_Name',defaultValue: 'main',description: 'Branches')
    }
    tools{
        maven 'maven3'
        jdk 'jdk17'
    }

    stages {
        stage('git checkout') {
            steps {
                git branch: "${params.Branch_Name}", url: 'https://github.com/munnakona/DevSecOps25.git'
            }
        }
        stage('Compile') {
            steps {
                sh 'mvn compile'
            }
        }
        stage('Test') {
            steps {
                echo 'mvn test'
            }
        }
        stage('Build') {
            steps {
                echo 'mvn package'
            }
        }
    }
}
