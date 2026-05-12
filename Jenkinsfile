pipeline {
    agent any

    stages {

        stage('Verificar herramientas') {
            steps {
                echo '🔍 Verificando Node y npm instalados...'
                bat 'node --version'
                bat 'npm --version'
            }
        }

        stage('Clonar repositorio') {
            steps {
                echo '📥 Clonando repositorio...'
                checkout scm
                echo '✅ Repo clonado correctamente'
            }
        }

        stage('Instalar dependencias') {
            steps {
                echo '📦 Instalando dependencias...'
                bat 'npm install'
                echo '✅ Dependencias instaladas'
            }
        }

        stage('Ejecutar pruebas') {
            steps {
                echo '🧪 Ejecutando pruebas...'
                bat 'npm test'
            }
        }

    }

    post {
        success {
            echo '🎉 ¡Pipeline completado exitosamente!'
        }
        failure {
            echo '❌ El pipeline falló. Revisá el Console Output.'
        }
        always {
            echo '🏁 Pipeline finalizado.'
        }
    }
}