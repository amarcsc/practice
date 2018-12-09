node{
    //checkout
    echo "$BRANCH_NAME"
    echo env.BRANCH_NAME
    stage('Checkout'){
       if ("$BRANCH_NAME".startsWith("master")){
       checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'amargit', url: 'https://github.com/amarcsc/learning.git']]])
       }
       else if("$BRANCH_NAME".startsWith("feature")){
         checkout([$class: 'GitSCM', branches: [[name: 'feature/jira-001']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'amargit', url: 'https://github.com/amarcsc/learning.git']]])
       }
      
    }
   
    
    //build
    stage('Build'){
         bat(/mvn  clean install/)
    
    }
}
