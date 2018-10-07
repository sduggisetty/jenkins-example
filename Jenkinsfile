node('master') {
    
    stage('cleanWs') {
        cleanWs()
    }
    
    stage 'Checkout'
    checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/sduggisetty/jenkins-example.git']]])

    
    stage('Build') {
        withAnt(installation: 'mywindows_ant1.9.6', jdk: 'JAVA_HOME') {
            bat 'ant'
        }
    
    
   input message: 'Do you want to clearn workspace?', ok: 'OK', submitter: 'subbu'
    
    stage('cleanWs') 
        cleanWs()
    }
    
    stage('Alrerts'){
            emailext body: '', subject: '', to: 'subbu@gmail.com'
    }
}
