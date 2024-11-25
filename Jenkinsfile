pipeline {

  agent any

  stages {
    stage('checkout') {
        steps {
            checkout scm
        }
    }

    stage('test') {
        steps {
            sh 'pwd'
        }
    }

    stage('Debug') {
        steps {
            // Debugging: Check for npm and node versions
            sh '''
                echo "Checking Node.js and npm versions"
                node -v
                npm -v
                which node
                which npm
            '''
        }
    }

    stage('Install Dependencies') {
        steps {
            // Install dependencies if npm is available
            sh '''
                if command -v npm >/dev/null 2>&1; then
                    echo "npm found, installing dependencies..."
                    npm install
                else
                    echo "npm not found, please install Node.js and npm!"
                    exit 1
                fi
            '''
        }
    }

    stage('deploy') {
        steps {
            sh 'pwd'
        }
    }
  }
}
