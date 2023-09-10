pipeline {
    agent any // Utiliza cualquier agente disponible

    stages {
        stage('Clonar Repositorio') {
            steps {
                // Clona el repositorio de tu código fuente desde Git
                checkout scm
            }
        }

        stage('Construir y Ejecutar Contenedor') {
            steps {
                // Construye la imagen Docker a partir del Dockerfile
                sh 'docker build -t mi-wordpress:latest .'

                // Ejecuta el contenedor a partir de la imagen construida
                sh 'docker run -d --name mi-wordpress -p 8080:80 mi-wordpress:latest'
            }
        }
    }

    post {
        success {
            // Este bloque se ejecutará si el pipeline se completa con éxito
            // Puedes agregar notificaciones o acciones adicionales aquí
        }
        failure {
            // Este bloque se ejecutará si el pipeline falla
            // Puedes agregar notificaciones o acciones adicionales aquí
        }
    }
}
