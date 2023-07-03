pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                //echo 'Hello World'
                bat  'rd /s /q  build'
                bat  'mkdir build'
                bat 'copy nul "build/car.txt"'
                bat 'echo "chassis" >> build/car.txt'
                 bat 'echo "engine" >> build/car.txt'
                  bat 'echo "body" >> build/car.txt'
                 
            }
        }
         stage('Test') {
            steps {
                bat 'if exist build/car.txt'
                bat 'find "chassis" build/car.txt'
                bat 'find "engine" build/car.txt'
                bat 'find "body" build/car.txt'
            }
        }
          stage('Publish') {
            steps {
             archiveArtifacts artifacts: 'build/'
            }
        }
    }
}
