node {      
    stage('Preparation') { 
        checkout scm
    }
    
    stage('Dependencies') {
        sh "ls"
    }

    stage ('Build xplat_dbapp_android_lxc') {
        build job: 'xplat_dbapp_android_lxc'
    }

    stage ('Build xplat_dbapp_ios_buck_unittest') {
        build job: 'xplat_dbapp_ios_buck_unittest'
    }
}
