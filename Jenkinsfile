pipeline {
  agent any
  tools { 
        maven 'Maven_3_8_4'  
    }
   stages{
    stage('CompileandRunSonarAnalysis') {
            steps {	
		sh 'mvn clean verify sonar:sonar -Dsonar.projectKey=wstran118_devsecops-jenkins-k8s-tf-sast-sonarcloud-repo -Dsonar.organization=wstran118 -Dsonar.host.url=https://sonarcloud.io -Dsonar.token=44db02eb00653b60abadca50b6d438ede51959e4'
			}
        } 
    stage('RunSCAAnalysisUsingSnyk') {
            steps {		
				withCredentials([string(credentialsId: 'SNYK_TOKEN', variable: 'SNYK_TOKEN')]) {
					sh 'mvn snyk:test -fn'
				}
	    }
  }
}
