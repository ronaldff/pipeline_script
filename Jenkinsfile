pipeline{
  agent none
  stages{
    stage('Non-Parallel Stage'){
      agent {
        label "master"
      }
      steps{
        echo "This stage will be executed first"
      }
    }
    
    stage('Run Tests'){
      parallel{
        stage('Tests on windows'){
           agent {
            label "Window_Nodes"
          }
          steps{
            echo "Task one on windows_node agent"
          }
        }
        stage('Tests on master'){
           agent {
            label "master"
          }
          steps{
            echo "Task two on master agent"
          }
        }
      }
    }
  }
}
