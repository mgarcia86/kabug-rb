pipeline {
    agent {
        docker {
            image 'ruby'
        }
    }

    stages{
        stage('Build') {
            steps {
                echo "Buildando ou resolvendo dependências"
                sh 'bundle install'
            }
        }
        stage('Testes') {
            steps {
                echo "Executando testes de regressão"
            }
        }
        stage('UAT') {
            steps {
                echo "Aguardando aceite do usuário"
                input(message: "Seguir para produção?", ok: "Sim")
            }
        }
        stage('Prod') {
            steps {
                echo "Aplicação apta a seguir para produção :)"
            }
        }
    }
}
