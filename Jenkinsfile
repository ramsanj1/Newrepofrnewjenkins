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
             sh "mvn compile"
         }
        }
        stage ("test")
        {
          steps
          {
              echo "testing the project"
              sh "mvn test"
          }
        }
        stage ("install")
        {
          steps
          {
              echo "installing the plugins"
              sh "mvn install"
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
