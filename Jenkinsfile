@Library('IM-Shared-Lib') _
pipeline{
    agent any
    stages{
        stage('SCM'){
            steps{
            //git clone/pull
                 git credentialsId: 'OneDevSlave', url: 'https://github.com/Pract-devops/WebTest', branch: 'dev'
                //Credentials("OneDevSlave","dev")
            }
           
        }
        stage('MVN'){
            steps{
                sh 'mvn clean package'
            }
        }
        stage('Tomcatdeploy'){
            steps{
                tomcatdeploy("172.31.85.44","ec2-user","myweb")
            }
        }
      
    }
}
