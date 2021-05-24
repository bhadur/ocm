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
                      #mkdir artifacts
                      #git clone https://github.com/bhadur/ocm.git
                      
                   '''
                }
    	    }
         
           stage('Pushing the image in repo') { 
            steps {
                echo 'Pushing the image to repositry'
                sh'''
                 pwd
                 ls
                '''
            }
        }
             
            stage('Scan: Checkmarx') {
                    steps{
                        echo "Executing Checkmarx Jenkins Plugin to request a Scan..."
                        step([$class: 'CxScanBuilder', comment: '', credentialsId: 'Checkmarx', excludeFolders: '', exclusionsSetting: '', failBuildOnNewResults: false, failBuildOnNewSeverity: 'HIGH', filterPattern: '''!**/_cvs/**/*, !**/.svn/**/*,   !**/.hg/**/*,   !**/.git/**/*,  !**/.bzr/**/*, !**/bin/**/*,
        !**/obj/**/*,  !**/backup/**/*, !**/.idea/**/*, !**/*.DS_Store, !**/*.ipr,     !**/*.iws,
        !**/*.bak,     !**/*.tmp,       !**/*.aac,      !**/*.aif,      !**/*.iff,     !**/*.m3u, !**/*.mid, !**/*.mp3,
        !**/*.mpa,     !**/*.ra,        !**/*.wav,      !**/*.wma,      !**/*.3g2,     !**/*.3gp, !**/*.asf, !**/*.asx,
        !**/*.avi,     !**/*.flv,       !**/*.mov,      !**/*.mp4,      !**/*.mpg,     !**/*.rm,  !**/*.swf, !**/*.vob,
        !**/*.wmv,     !**/*.bmp,       !**/*.gif,      !**/*.jpg,      !**/*.png,     !**/*.psd, !**/*.tif, !**/*.swf,
        !**/*.jar,     !**/*.zip,       !**/*.rar,      !**/*.exe,      !**/*.dll,     !**/*.pdb, !**/*.7z,  !**/*.gz,
        !**/*.tar.gz,  !**/*.tar,       !**/*.gz,       !**/*.ahtm,     !**/*.ahtml,   !**/*.fhtml, !**/*.hdm,
        !**/*.hdml,    !**/*.hsql,      !**/*.ht,       !**/*.hta,      !**/*.htc,     !**/*.htd, !**/*.war, !**/*.ear,
        !**/*.htmls,   !**/*.ihtml,     !**/*.mht,      !**/*.mhtm,     !**/*.mhtml,   !**/*.ssi, !**/*.stm,
        !**/*.stml,    !**/*.ttml,      !**/*.txn,      !**/*.xhtm,     !**/*.xhtml,   !**/*.class, !**/*.iml, !Checkmarx/Reports/*.*''', fullScanCycle: 10, generatePdfReport: true, groupId: '22f6feaa-42cb-4380-bd7e-a01e731963d6', incremental: true, password: '{AQAAABAAAAAQ8XxXXENRwXzkeu3OgW5AArK9jpEKqIyhZeQx3OuXS9c=}', preset: '36', projectName: 'authentication-ms', sastEnabled: true, serverUrl: 'https://sast.intel.com/', sourceEncoding: '1', useOwnServerCredentials: true, username: '', vulnerabilityThresholdResult: 'FAILURE', waitForResultsEnabled: true])
       
                    sh '''
                        cp Checkmarx/Reports/* artifacts/
                        zip -r checkmarx.zip Checkmarx/
                    '''
                    }
       
        }
     }
}

    
