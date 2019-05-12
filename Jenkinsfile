pipeline {
    agent any


    stages {
        stage('SCM Checkout'){
          git 'https://github.com/amitkapadnisamit/maven-project'
        }
  }
	
	{
	stage ('package') {
            steps {
                withMaven(maven : 'MavenAmit') {
                    sh 'mvn package'
                }
            }
        }	

	stage('SonarQube analysis') {
       withSonarQubeEnv('Sonar') {
	       withMaven(maven : 'MavenAmit') {
      sh 'mvn clean package sonar:sonar'
    } 
    }
  }
}
}
