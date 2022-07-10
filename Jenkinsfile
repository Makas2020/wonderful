node {

    def mvnHome = tool 'Maven2'
    stage ("checkout")  {
        git 'https://github.com/Makas2020/wonderful.git' 
    }
    stage ('build')  {
    sh "${mvnHome}/bin/mvn clean install -f MyWebApp/pom.xml"
    }
     stage ('Code coverage')  {
       jacoco()
   }
    
    stage ('Code quality scan') {
     withSonarQubeEnv('Sonar30') {
     sh "${mvnHome}/bin/mvn sonar:sonar -f MyWebApp/pom.xml"
      }
   
    }
         
    

  }
