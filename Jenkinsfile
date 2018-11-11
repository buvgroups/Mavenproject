#!groovy

node {
	   
	stage('Checkout'){

          checkout scm
       }

  /*     
    stage("checkout scm")
    {
        git branch: 'stage', credentialsId: 'c8d7b18f-a25e-4761-b9a2-f029a40d98be', url: 'https://github.com/HPEProject/Maven-web-project.git'

    } */
    stage("maven test")
    {
        bat 'mvn clean'
    }
    stage("build")
    {
        bat 'mvn clean install'
    }
    stage("sonarqube")
    {
        bat 'mvn sonar:sonar'
    }
    stage("deploy into nexus")
    {
        bat 'mvn deploy'
    }
    stage("deploy into tomcat")
    {
        echo "deploying into tomcat server"
        bat 'copy %WORKSPACE%\\target\\*.war C:\\Devopssoftware\\Tomcat\\apache-tomcat-9.0.12\\webapps'
    }
   /* stage("e-mail notification")
    {
        mail bcc: 'vknkv@gmail.com', body: 'successfully runing', cc: 'kvpavan9@gmail.com', from: '', replyTo: '', subject: 'script runing success', to: 'praveenkumar1290.mohan@gmail.com'

    }*/
}
	
       
