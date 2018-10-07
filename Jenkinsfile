node('master') {
    stage 'Clean workspace'
    bat 'del /s /q /f *.*'
    
    stage 'Checkout'
    checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/sduggisetty/jenkins-example.git']]])

    
    stage 'Compile'
    withAnt(installation: 'Ant1.9.0') {
        bat 'ant'
    }
	
    stage 'Archieving'
    archiveArtifacts '*.jar'
}
