pipeline {
  agent any
  tools { 
        maven 'Maven_3_5_2'  
    }
   stages{
    stage('CompileandRunSonarAnalysis') {
            steps {	
		sh 'mvn clean verify sonar:sonar -Dsonar.projectKey=wstran118_devsecops-jenkins-k8s-tf-sast-sonarcloud-repo -Dsonar.organization=wstran118 -Dsonar.host.url=https://sonarcloud.io -Dsonar.token=44db02eb00653b60abadca50b6d438ede51959e4'
			}
        } 
  }
}
