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
                  TAG=$BUILD_TAG


       sudo docker info
sudo  docker build . --tag $APP
sudo  docker tag $APP $CI_REGISTRY_USER/$APP:$TAG

                
                echo "indiplom"
                
                '''
                               
            }
        }  
    }
}
