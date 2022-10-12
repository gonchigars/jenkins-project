pipeline{
    //Directives
    agent any
    tools {
        maven 'maven'
    }
  
    stages {
        // Specify various stage with in stages

        // stage 1. Build
        stage ('Build'){
            steps {
                sh 'mvn clean install package'
            }
        }

        // Stage2 : Testing
        stage ('Test'){
            steps {
                echo ' testing.........'

            }
        }
        
        // Stage3: Publish to Nexus
        stage ('Publish to Nexus'){
            steps {
                nexusArtifactUploader artifacts: [[artifactId: 'DevopsLab', classifier: '', file: 'target/DevOpsLab-0.0.14--SNAPSHOT.war', type: '  war']], credentialsId: '830ed2f2-73f4-4350-b781-b70666863bb1', groupId: 'com.devopslab', nexusUrl: '18.206.187.46:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'DevOpsLab-SNAPSHOT', version: '0.0.14-SNAPSHOT'

            }
        }

       // Stage4 : Deploying
        stage ('Deploy'){
            steps {
                echo ' Deploying......'

            }
        }


//stages
    }

}
