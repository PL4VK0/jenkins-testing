pipeline {
    agent any
    stages {
        stage('Installing apache2'){
            steps {
                echo "###### INSTALLING APACHE2 #####"
                try {
                  bash 'apt install -y apache2'
                  echo "###### INSTALLING APACHE2 #####"
                } catch (exc) {
                    echo "##### FAILED INSTALLING APACHE2!!! #####"
                  }
              }
          }
          stage('Checking 4xx and 5xx errors'){
              steps {
                  echo "##### SCANNING FOR ERRORS #####"
                  sh '''awk '$9 ~ /4[0-9]{2}|5[0-9]{2}/ {print $0}' /var/log/apache2/access.log '''
                }
            }
      }
  }
