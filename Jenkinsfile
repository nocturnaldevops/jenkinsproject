pipeline
{
   agent any
   stages
   {
        stage("contdownload")
        {
             steps
             {
             git branch: 'main', url: 'https://github.com/nocturnaldevops/Projectnew.git'
              }
          }
        stage("contbuild")
        {
             steps
             {
             sh 'mvn package'
              }
          }
        stage("contdeploy")
        {
             steps
             {
              deploy adapters: [tomcat9(credentialsId: '8d3ecba5-efe9-47ff-bb33-3bbecc06492c', path: '', url: 'http://172.31.2.65:8080')], contextPath: 'testapp', war: '**/*.war'
              }
          }
        stage("conttest")
        {
             steps
             {
              sh 'echo "testing passed"'
              }
          }
        stage("contdelivery")
        {
             steps
             {
             deploy adapters: [tomcat9(credentialsId: '8d3ecba5-efe9-47ff-bb33-3bbecc06492c', path: '', url: 'http://172.31.14.74:8080')], contextPath: 'release101', war: '**/*.war'
              }
          }
      }
}
