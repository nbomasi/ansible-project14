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

ansible.cfg
[defaults]
timeout = 160
roles_path = /home/ubuntu/config-mgt-ansible/roles
callback_whitelist = profile_tasks
log_path=~/ansible.log
host_key_checking = False
gathering = smart

[ssh_connection]
ssh_args = -o ControlMaster=auto -o ControlPersist=30m -o ControlPath=/tmp/ansible-ssh-%h-%p-%r -o ServerAliveInterval=60 -o ServerAliveCountMax=60
