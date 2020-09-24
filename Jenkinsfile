node {      
    stage('Preparation') { 
        git credentialsId: '3ab81c0f-a1b4-4fac-8a19-300b1b1ea30a', url: 'git@github.com:changusmc/plaid.git'
    }
    
    stage('Dependencies') {
        sh "ls"
    }
    
    stage('Clean Build') {
        sh "pwd"
        sh 'ls -al'
        sh './gradlew clean'
    }
    
    stage('Build debug ') {
        dir("android") {
            sh './gradlew assembleDebug'
        }
    }
    
    stage('Compile') {
        archiveArtifacts artifacts: '**/*.apk', fingerprint: true, onlyIfSuccessful: true            
    }
}