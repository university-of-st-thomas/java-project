properties([pipelineTriggers([githubPush()])]) 
node('linux'){
    stage('Build'){
        git 'https://github.com/thaer665/java-project.git'
        sh "ant"
    }
    
    stage('Test'){
        sh "ant -buildfile test.xml"
    }
    
    stage('Reports'){
        junit 'reports/*.xml'
    }
}
