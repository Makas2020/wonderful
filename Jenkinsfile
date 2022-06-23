node {

    def mvnHome = tool 'Maven3'
    stage ("checkout")  {
        git 'https://github.com/Makas2020/wonderful.git' 
    }
    stage ('build')  {
    sh "${mvnHome}/bin/mvn clean install -f MyWebApp/pom.xml"
    }
     stage ('Code coverage')  {
       jacoco()
   }
     stage ('DEV Deploy')
    {
                echo "deploying to DEV tomcat "
               sh 'sudo cp /var/lib/jenkins/workspace/$JOB_NAME/MyWebApp/target/MyWebApp.war /var/lib/tomcat8/webapps'
    }


  }
