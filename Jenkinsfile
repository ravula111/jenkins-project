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
                nexusArtifactUploader artifacts: [[artifactId: 'DevopsLab', classifier: '', file: 'target/maven-java.war', type: 'war']], credentialsId: 'bab75d51-1f66-4cca-ba58-9749781a0d38', groupId: 'com.devopslab', nexusUrl: '3.80.57.150:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'maven-java', version: '0.0.14-SNAPSHOT'

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
