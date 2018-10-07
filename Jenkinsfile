node('master') {
    stage 'Clean workspace'
    bat 'del /s /q /f *.*'
    
    stage 'Checkout'
    checkout([$class: 'SubversionSCM', additionalCredentials: [], 
    excludedCommitMessages: '', excludedRegions: '', 
    excludedRevprop: '', excludedUsers: '', 
    filterChangelog: false, ignoreDirPropChanges: false, 
    includedRegions: '', locations: [[credentialsId: '34e09eb8-7774-445f-a812-799fd5e03792', depthOption: 'infinity', ignoreExternalsOption: true, local: '.', 
    remote: 'http://venkateswarlu/svn/ant_proj/trunk']], 
    workspaceUpdater: [$class: 'UpdateUpdater']])
    
    stage 'Compile'
    withAnt(installation: 'Ant1.9.0') {
        bat 'ant'
    }
	
    stage 'Archieving'
    archiveArtifacts '*.jar'
}
