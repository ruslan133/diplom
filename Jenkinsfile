pipeline {
    agent any

    stages {
        stage('билди приложуху') {
            steps {
              
                sh '''
                rm -rf diplom
                git clone https://github.com/ruslan133/diplom.git
                cd diplom
                APP=diplom_app
                TAG=$BUILD_ID                  
                sudo docker info
                sudo  docker build . --tag $APP
                sudo  docker tag $APP ruslan133/$APP:$TAG
                '''                               
            }
        }  
        stage('Push ee') {
            steps {
               
                sh '''                
                cd diplom
                sudo docker info
                sudo docker login -u ruslan133 -p 19781805Rus
                APP=diplom_app
                TAG=$BUILD_ID
                sudo sudo service docker restart
                sudo docker push ruslan133/$APP:$TAG
                '''
                               
            }
        } 
         stage('deploy ee') {
            steps {
               
                sh '''                
                cd diplom
                cp /var/lib/jenkins/arch/diplom/id_rsa .
                APP=diplom_app
                TAG=$BUILD_ID
                ssh -o StrictHostKeyChecking=no  admin@62.84.114.157 "sudo helm upgrade app /root/kuber/helm --set app_image=ruslan133/$APP:$TAG" -i id_rsa
                '''
                               
            }
        }  
    }
}
