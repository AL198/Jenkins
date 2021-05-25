pipeline {
         agent any
         stages {
                 stage('Build') {
                 steps {
                     sh 'sudo yum install -y httpd&& sudo firewall-cmd --permanent --add-service=http&& sudo firewall-cmd --reload'
                 }
                 }
                 stage('Test') {
                 steps {
                    input('Httpd was installed')
                 }
                 }
                 stage('Run') {
      steps {
        sh 'sudo systemctl start httpd&& sudo systemctl enable httpd'
      }
    }
                 stage('Prod') {
                     steps {
                                sh 'echo "<h1>This is your newly created webserver using jenkins</h1>" > /var/www/html/index.html'
                              }
                 
              }
              stage('End') {
      steps {
        echo 'End of pipeline'
      }
    }
         }
}
