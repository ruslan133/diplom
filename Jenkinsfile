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
                echo "indiplom"
                
                '''
                               
            }
        }  
    }
}
