pipeline{
    agent any
    tools
    {
        maven 'apache-maven-3.3.3'
        jdk 'JDK'
    }
    stages{
        stage ("build")
        {
         steps
         {
             echo " build a project."
             sh 'cd MavenProject ; mvn compile ; pwd'
         }
        }
        stage ("test")
        {
          steps
          {
              echo "testing the project"
              sh 'cd MavenProject ; mvn test ; pwd'
          }
        }
        stage ("install")
        {
          steps
          {
              echo "installing the plugins"
              sh 'cd MavenProject ; mvn install ; pwd'
          }
        }
        stage ("clean up")
        {
          steps
          {
              echo "cleaninig up workspace"
               cleanWs()
          }
        }
    }
}
