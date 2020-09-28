pipeline {
    agent any
    
    stages {
        stage('Preparation') { 
            steps {
                checkout scm
            }
        }
        
        stage('Dependencies') {
            steps {
                sh "ls"
            }
        }

        stage ('Build xplat_dbapp_android_lxc') {
            when { 
                anyOf {
                    changeset "jenkins/xplat_dbapp_android_lxc/**"
                }
            }

            steps {
                build job: 'xplat_dbapp_android_lxc'
            }
        }

        stage ('Build xplat_dbapp_ios_buck_unittest') {
            when { 
                anyOf {
                    changeset "jenkins/xplat_dbapp_ios_buck_unittest/**"
                }
            }        
            steps {
                build job: 'xplat_dbapp_ios_buck_unittest'
            }
        }
    }
}
