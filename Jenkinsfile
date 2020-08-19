				
				node {
   
    stage('Scm Checkout') {
        git credentialsId: 'git-creds', url: 'https://github.com/severino-on/teste'
    }
    stage('Mvn Pakage') {
        def mvnHome = tool name: 'maven-3', type: 'maven'
        def mvnCMD = "${mvnHome}/bin/mvn"
        sh "${mvnCMD} clean package"
        sh "${mvnCMD} test package"
        
    }
    stage(cucumber report){
        cucumber failedFeaturesNumber: -1, failedScenariosNumber: -1, failedStepsNumber: -1, fileIncludePattern: '**/*.json', pendingStepsNumber: -1, skippedStepsNumber: -1, sortingMethod: 'ALPHABETICAL', undefinedStepsNumber: -1
    }
 
}