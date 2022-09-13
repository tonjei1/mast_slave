pipeline{
  agent {
    label {
      label 'slave1'
    }
  }
  stages{
    stage('version-control'){
      steps{
        checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'github-id', url: 'https://github.com/team3Group2EtechApp/master_slave_job.git']]])
      }
    }
    stage('parallel-job'){
      parallel{
        stage('sub-job1'){
          steps{
            echo 'action1'
          }
        }
        stage('sub-job2'){
          steps{
            echo 'action2'
          }
        }        
      }
    }
  stage('codebuild'){
    steps{
      agent {
        label 'slave2'
      }
    }
  }
  stage('Unit-testing'){
      steps{
        sh 'cat /etc/passwd'
      }   
  }
  stage('sub-job3'){
      steps{
          echo 'action3'
      }
  }
    
  stage('codes'){
    steps{
      agent {
        label 'slave2'
      }
    }
  }
  stage('Unit-tes'){
      steps{
        sh 'cat /etc/passwd'
      }   
  }
  stage('sub'){
      steps{
          echo 'action3'
      }
  }
  }
}
