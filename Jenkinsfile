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

         
}
}
