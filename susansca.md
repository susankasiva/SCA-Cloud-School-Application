pipeline {
    agent any

    stages {
        
        stage(' Source') {
            steps {
        script:
                
                bat'git clone --single-branch --branch develop https://github.com/susankasiva/SCA-Cloud-School-Application.git'
                echo 'Cloning Project'
                bat
                cd project_folder
                npm install
            }
        }
        stage('Install') {
            steps {
        script:
              bat 'mvm install -f sca game'
                
            }
        }
        stage('Build') {
            steps { 
                script:
              echo "Compiling the code..."
              echo "Compile complete."
            }
        
        }
            
                
    
        stage('Deploy') {
            steps {
        script:
              - echo "Deploying application..."
              - echo "Application successfully deployed."
            }
        } 
        stage('Test') {
            steps {
        script:
                bat 'mvm test -f sca game'
                echo 'Testing'
            }
        }
        stage('Package') {
            steps {
        script:
                 bat mvm 'package -f sca game'
                 echo "Packaging the code..."
                
            }
        }
    }
}

