pipeline{
    agent { labels "jenkins-slave"}
    tools{
        jdk 'openjdk'
        maven 'maven'
    }
stages{
    stage("cleanup workspace"){
        steps{
            cleanWs()
        }
    }
    stage("checkout from git"){
        steps{
            git branch: 'main', credentialsId: 'github', url: 'https://github.com/Sarulatha59/register-app'
        }
    }
    stage("Building application"){
        steps{
            sh "mvn clean package"
        }
    }
    stage("Testing application"){
        steps{
            sh "mvn test"
        }
    }
}
}
          
