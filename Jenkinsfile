pipeline {
    agent {
        node {
          label 'master'
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
                   sh '''#!/bin/bash
                      uname -a
                      mkdir artifacts
                      git clone https://github.com/bhadur/openvino_tensorflow-1.git
                      
                   '''
                }
    	    }
  
    
     }

  }
