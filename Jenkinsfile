node {

    def mvnHome = tool 'Maven3'
    stage ("checkout")  {
        git 'https://github.com/Makas2020/wonderful.git' 
    }
    stage ('build')  {
    sh "${mvnHome}/bin/mvn clean install -f MyWebApp/pom.xml"
    }
    
  }
