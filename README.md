# config-mgt-ansible
Ansible Configuration Management

## ////////////////////////////////////////
Task jekinsfile:

pipeline {
    agent any

  
  stages {
    stage('Pre-Build Cleanup') {
      steps {
        cleanWs() // Clean up workspace before the build starts
            }
        }

    stage('Build') {
      steps {
        script {
          sh 'echo "Building Stage"'
        }
      }
    }

    stage('test') {
      steps {
        script {
          sh 'echo "Testing Stage"'
        }
      }
    }

    stage('package') {
      steps {
        script {
          sh 'echo "To package application"'
        }
      }
    }

    stage('deploy') {
      steps {
        script {
          sh 'echo "To deploy application"'
        }
      }
    }

   // stage('Post-Build Cleanup') {
   //   steps {
     //   cleanWs() // Clean up workspace after the build completes
    //        }
     //   }
    }
}
