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

        stage ('publish to nexus') {
          steps {
            nexusArtifactUploader artifacts: [[artifactId: 'cicdlab', classifier: '', file: 'target/cicdlab-0.0.9.war', type: 'war']], credentialsId: '', groupId: 'com.vigneshdevopssession', nexusUrl: '172.31.28.237:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'artifact-RELEASE', version: '0.0.9'
          }
        }

        // Stage3 : Publish the source code to Sonarqube
        stage ('deploy'){
            steps {
                echo 'Deploying'
                }

            }
        }



    }
