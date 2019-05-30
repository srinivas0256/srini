pipeline {
    agent any
    tools { 
        maven 'maven' 
        jdk 'jdk' 
    }
    stages {
        stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                ''' 
            }
        }

        stage ('scm') {
            steps {
                git credentialsId: '4db8806c-2e01-48c4-afd3-bc152e3fe803', url: 'https://github.com/srinivas0256/srini.git'
            }
        }
        
        stage ('build') {
            steps {
                sh 'mvn clean install'
            }
		}
    }
}
