pipeline {
    agent {
        node {
          label 'EdgeCSP_01'
        }
      
    }
   
    environment {
        GITLAB_LOGIN = credentials('Intel-Gitlab')
        PROTEX_LOGIN = credentials('protex_credentials')
        PROTEX_PROJECT = "c_ocm_tf_21125"
        PROTEX_SERVER = "amrprotex004.devtools.intel.com"
        CURRENT_DATE = sh(script: 'date +%Y%m%d', returnStdout: true).trim()
        PROJECT_NAME = "ocm" //Needs to be similar to Gitlab Project name
        GitHub_Token = credentials('ocm_github_token')
        GITLAB_BRANCH = "master"
        Workspace="/home/ubuntu/workspace/EdgeCSP/OCM"
        BDBA_Token = credentials('BDBA_Up_Dl')

    }
    
     stages {
     stage('Checkout SCM') {
            steps{
                sh '''
                cd /home/ubuntu/workspace/EdgeCSP/test_job
                #rm -rf *
                pwd
                ls
                printenv | sort
                pwd
                echo $WORKSPACE
                echo "test2"
                '''
            }
  
    
     }
}
  }
