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
        stage('Копирую к себе репы с GIT') {
            steps {
               
                sh '''
                cd diplom
                docker info
                docker login -u ruslan133 -p 19781805Rus
                APP=diplom_app
                TAG=$BUILD_ID
                docker push ruslan133/$APP:$TAG
                '''
                               
            }
        }  
    }
}
