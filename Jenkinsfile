pipeline {
    agent any

    stages {
        
        stage(' Source') {
            steps {
                bat'git clone --single-branch --branch develop https://github.com/susankasiva/SCA-Cloud-School-Application.git'
                echo 'Cloning Project'
                cd project_folder
                npm install
            }
        }
        stage('Install') {
            steps {
              echo "Installing"
                
            }
        }
        stage('Build') {
            steps { 
              echo "Compiling the code..."
              echo "Compile complete."
            }
        
        }     
        stage('Deploy') {
            steps {
              echo "Deploying application..."
              echo "Application successfully deployed."
            }
        } 
        stage('Test') {
            steps {
               bat 'mvm test -f sca game'
               echo "Testing"
            }
        }
        stage('Package') {
            steps {
              echo "Packaging the code..."
                
            }
        }
    }
}

