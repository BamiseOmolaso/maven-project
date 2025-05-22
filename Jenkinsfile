pipeline {
    agent {
        label 'DevServer'
    }

    parameters {
      string defaultValue: 'omolaso', name: 'LASTNAME'
    }

    environment{
        NAME = "bamise"
    }
    
    tools {
        maven 'mymaven'
    }

    stages {
        
        stage('Build') 
        {
            steps {
                sh 'mvn clean package'
                echo hello $NAME ${params.LASTNAME}
            }

            post {
            success {
                archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }
    }
}
