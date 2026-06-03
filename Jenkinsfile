pipeline {

    agent any

    parameters {

        string(
            name: 'BRANCH_NAME',
            defaultValue: 'main',
            description: 'Git Branch Name'
        )

        string(
            name: 'APP_VERSION',
            defaultValue: '1.0',
            description: 'Application Version'
        )
    }

    environment {

        BUILD_DIR = "build"

        ARTIFACT_NAME = "demo-app.jar"
    }

    stages {

        stage('Checkout') {

            steps {

                echo "Checking out branch: ${params.BRANCH_NAME}"

            }
        }

        stage('Build') {

            steps {

                echo "Building Application"

                bat 'if not exist build mkdir build'

                bat 'echo Build Successful > build\\output.txt'
            }
        }

        stage('Unit Testing') {

            steps {

                echo "Running Unit Tests"

                bat 'echo Tests Passed'
            }
        }

        stage('Code Quality Check') {

            steps {

                echo "Performing Code Quality Check"

                bat 'echo Code Quality Passed'
            }
        }

        stage('Artifact Packaging') {

            steps {

                echo "Packaging Artifact"

                bat 'type nul > build\\demo-app.jar'
            }
        }
    }

    post {

        success {

            echo 'Pipeline Executed Successfully'
        }

        failure {

            echo 'Pipeline Failed'
        }
    }
}
