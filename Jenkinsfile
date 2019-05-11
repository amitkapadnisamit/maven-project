pipeline {
    agent any


    stages {
        stage('SCM Checkout'){
          git 'https://github.com/amitkapadnisamit/maven-project'
        }
  }
    {
        stage ('Compile Stage') {

            steps {
                withMaven(maven : 'MavenAmit') {
                    sh 'mvn clean compile'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'MavenAmit') {
                    sh 'mvn test'
                }
            }
        }


        stage ('install Stage') {
            steps {
                withMaven(maven : 'MavenAmit') {
                    sh 'mvn install'
                }
            }
        }
        stage('deply to tomcat') {
            steps {
                     sshagent(['409f5400-8590-487a-8ecf-6e58f7ac2f15']) {
                  sh 'scp -o StrictHostKeyChecking=no */target/*.war es2-user@172.31.33.117:/var/lib/tomcat/webapps'
                        }
                  }

         }
}
