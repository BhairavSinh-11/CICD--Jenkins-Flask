pipeline {
    agent any

    stages {
        stage('install docker-compose') {
            steps {
                script{
                    sh ''' 
                        apt update 

                        if ! command -v docker &> /dev/null
                        then
                            echo "Docker not found, installing..."
                        else
                            echo "Docker is already installed."
                        fi
                        
                        apt install docker.io -y

                        if ! command -v docker-compose &> /dev/null
                        then
                            echo "docker-compose not found, installing..."
                        else
                            echo "docker-compose is already installed."
                        fi
                        
                        apt install docker-compose -y
                        
                    '''
                }
            }
        }
        stage('Deploy') {
            steps {
                withCredentials([file(credentialsId: 'jenkins-env-file', variable: 'ENV_FILE_PATH')]) {
                    sh '''
                        # Copy secret file to .env

                        cp $ENV_FILE_PATH .env

                        docker-compose --env-file .env down 

                        DOCKER_BUILDKIT=0 docker-compose --env-file .env build
                        
                        docker-compose --env-file .env up -d
                    '''
                }
            }
        }
        
        // use this if db is not initialized by the application itself, otherwise it will throw an error because the db is already initialized
        // stage('Initialize Database') {
        //     steps {
        //          withCredentials([file(credentialsId: 'jenkins-env-file', variable: 'ENV_FILE_PATH')]) {
        //         dir('/app'){
        //             sh '''
        //                 # Load environment variables from .env file
        //                 cp $ENV_FILE_PATH .env
        //                 sed -i 's/\r$//' .env 

        //                 export $(cat .env | xargs)

        //                 sleep 15

        //                 docker exec -i mysql_db mysql \
        //                     -u root \
        //                     -p${MYSQL_ROOT_PASSWORD} \
        //                     ${MYSQL_DATABASE} < schema.sql
        //             '''
        //          }
        //         }
        //     }
        // }
    }
}