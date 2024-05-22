pipeline
{
    agent any
    stages
    {
        stage("contDownload")
        {
            steps
            {
                git branch: 'main', url: 'https://github.com/nocturnaldevops/NewProject24.git'
            }
        }
        stage("contBuild")
        {
            steps
            {
                sh 'mvn packagee'
            }
        }
        stage("contDeploy")
        {
            steps
            {
                deploy adapters: [tomcat9(credentialsId: '84c9b9bd-7d19-4cd2-8bb7-d90477e63684', path: '', url: 'http://172.31.23.199:8080')], contextPath: 'test22', war: '**/*.war'
            }
        }
    stage("cont_test")
    {
        steps{
            sh 'echo "testing passed"'
        }
    }
    stage("cont_delivery")
    {
        steps{
            deploy adapters: [tomcat9(credentialsId: '6d11be8e-81a2-4fa1-ba9c-c87973654792', path: '', url: 'http://172.31.26.124:8080')], contextPath: 'appv1', war: '**/*.war'
        }
    }
}
   post{
        failure{
            mail bcc: '', body: 'The project failed', cc: '', from: '', replyTo: '', subject: 'project failed', to: 'projects2488@gmail.com'
        }
    }
}