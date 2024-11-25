pipeline {

  agent any

//   environment {
//       NVM_DIR = '/home/scibdlog/.nvm'
//   }

  environment {
      NVM_DIR = '/root/.nvm'
  }

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
                bash -c "which node && which npm"
            '''
        }
    }

    // stage('Install Dependencies') {
    //     steps {
    //         // Install dependencies if npm is available
    //         sh '''
    //             bash -c "source $NVM_DIR/nvm.sh && if command -v npm >/dev/null 2>&1; then
    //                 echo 'npm found, installing dependencies...'
    //                 npm install  && docker compose down && docker compose up -d
    //             else
    //                 echo 'npm not found, please install Node.js and npm!'
    //                 exit 1
    //             fi"
    //         '''
    //     }
    // }

    stage('Install Dependencies') {
        steps {
            // Install dependencies and restart Docker containers
            sh '''
                echo "Stopping and starting Docker containers..."
                docker compose down || echo "Failed to stop containers or no containers were running."
                docker compose up -d || exit 1
                echo "Docker containers restarted successfully."
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
