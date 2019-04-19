properties([pipelineTriggers([githubPush()])]) 
node('linux'){
    stage('Build'){
        git credentialsId: '62f7d6fb-eaed-4554-8a5b-fbc1c88d1d2b', url: 'http://github.com/thaer665/PrivateRepo.git'
        sh "ant"
    }
    
    stage('Test'){
        sh "ant -buildfile test.xml"
    }
    
    stage('Reports'){
        junit 'reports/*.xml'
    }
}
