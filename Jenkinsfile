pipeline {
    agent any

    stages {
        stage('Копирую к себе репы с GIT') {
            steps {
               sh '' 
                sh '''
                rm -rf diplom
                git clone https://github.com/ruslan133/diplom.git
                cd diplom

                  APP=diplom_app
                  TAG=$BUILD_ID


       sudo docker info
sudo  docker build . --tag $APP
sudo  docker tag $APP ruslan133/$APP:$TAG

                
                echo "indiplom"
                
                '''
                               
            }
        }  
    }
}
