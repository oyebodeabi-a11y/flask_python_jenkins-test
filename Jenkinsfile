pipeline{
    agent any
    stages{
         stage("GitHub checkout") {
            steps {
                script {
 
                    git branch: 'main', url: 'https://github.com/oyebodeabi-a11y/flask_python_jenkins-test.git' 
                }
            }
        }
        stage("Build docker on going"){
            steps{
                sh 'printenv'
                sh 'git version'
                sh 'docker build . -t abiprojectalone1/imag1.0'
            }
        }
         stage("push image to DockerHub"){
            steps{

               script {
                  
                 withCredentials([string(credentialsId: 'dockerID', variable: 'dockerID')]) {
                    sh 'docker login -u abiprojectalone1 -p ${dockerID}'
            }
              sh 'docker push abiprojectalone1/imag1.0:latest'
            }
        }
    }
    }
}

    
