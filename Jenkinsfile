node('master') {
    
    stage('cleanWs') {
        cleanWs()
    }
    
    stage 'Checkout'
    checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/sduggisetty/jenkins-example.git']]])

    
    stage('Build') {
        withAnt(installation: 'ant1.9.6', jdk: 'mywindows_jdk1.8') {
            bat 'ant'
        }
    }
    

   /////input message: 'Do you want to clearn workspace?', ok: 'OK', submitter: 'subbu'

    stage('cleanWs') {
        cleanWs()
    }
    
    stage('Alrerts'){
            emailext body: '', subject: '', to: 'subbu@gmail.com'
    }
}


