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
                echo ' testing......'

            }
        }
        
        // Stage3: Publish to Nexus
        stage ('Publish to Nexus'){
            steps {
                nexusArtifactUploader artifacts: [[artifactId: 'DevopsLab', classifier: '', file: 'target/DevopsLab-0.0.13-SNAPSHOT.war', type: 'war']], credentialsId: 'b1d490c8-a766-46a0-bb9b-4b2d1756d879', groupId: 'com.devopslab', nexusUrl: '172.31.82.24:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'DevOpsLab-SNAPSHOT', version: '0.0.12-SNAPSHOT'

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
