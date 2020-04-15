pipeline{ 
    agent any
    tools {
        maven 'Maven'
        jdk 'JDK'
    }
    stages {
        stage ("clone"){
            steps {
                echo "cloning the project"
                git 'https://github.com/ramsanj1/Newrepofrnewjenkins.git'
            }
        }
            stage ("build"){
            steps {
                echo "build the project"
                sh 'cd MavenProject ; mvn clean compile package ; pwd'
            }
            }
            stage ("Archive"){
            steps {
                echo "Archive the Artifacts"
                archiveArtifacts '**/*.war'
            }
            }
            stage ("Deploy"){
            steps {
                echo "deploy the project"
                deploy adapters: [tomcat8(credentialsId: 'f01d7b17-d5e9-4a46-ab98-e26f63bf7582', path: '', url: 'http://40.122.206.199:8080')], contextPath: null, war: '**/*.war'
            }
            }
            stage ("post"){
            steps {
                echo "emailing the build status"
                emailext body: 'Build status success', subject: 'Build status', to: 'sandhya@devopsenabler.com'
            }
            }
    }
}
