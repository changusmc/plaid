node {      
    stage('Preparation') { 
        checkout scm
    }
    
    stage('Dependencies') {
        sh "ls"
    }

    stage ('Invoke_pipelineA') {
        build job: 'Scripts Pipeline'
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