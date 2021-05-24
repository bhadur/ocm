pipeline {
    agent {
        node {
          label 'master'
        }
      
    }
   
      
     stages {
            stage('Checkout SCM') {
               steps{
                   sh '''#!/bin/bash
                      uname -a
                      mkdir artifacts
                      git clone https://github.com/bhadur/ocm.git
                      
                   '''
                }
    	    }
  
    
     }

  }
