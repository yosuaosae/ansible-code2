pipeline{
    agent any 


    stages{
        stage('zip the file'){
            steps{
                sh 'rm -rf *.zip || echo ""'
                sh 'zip ansible-${BUILD_ID}.zip * --exclude jenkinsfile'
                sh 'ls -l'
            }
        }
        stage ('upload artifacts to jfrog'){
            steps{
                sh 'curl -uadmin:APBcq71UnokyUif1o4U46B5LuEZ -T ansible-${BUILD_ID}.zip \
                 "http://54.156.126.227:8081/artifactory/ansible/ansible-${BUILD_ID}.zip"'
            }
        }
    }
}