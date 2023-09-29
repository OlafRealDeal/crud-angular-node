pipeline {
    agent any

    stages {
        stage('Clonar Repositorio') {
            steps {
                script {
                    checkout scm
                }
            }
        }

        stage('Compilar y Construir Cliente') {
            steps {
                script {
                    dir('cliente') {
                        // Entrar al directorio del cliente
                        bat 'npm install'
                        bat 'ng build --prod'
                    }
                }
            }
        }

        stage('Compilar y Construir Servidor') {
            steps {
                script {
                    dir('servidor') {
                        // Entrar al directorio del servidor
                        bat 'npm install'
                        // Puedes ejecutar aquí cualquier comando necesario para construir el backend
                    }
                }
            }
        }

        stage('Ejecutar Pruebas Unitarias') {
            steps {
                script {
                    dir('cliente') {
                        // Entrar al directorio del cliente
                        bat 'ng test'
                    }
                    dir('servidor') {
                        // Entrar al directorio del servidor
                        // Ejecutar pruebas del backend si las hay
                    }
                }
            }
        }

        // stage('Generar y Publicar Contenedores Docker') {
        //     steps {
        //         script {
        //             dir('cliente') {
        //                 // Construir imagen Docker para el cliente (Angular)
        //                 bat 'docker build -t tu_usuario/cliente .'
        //                 bat 'docker push tu_usuario/cliente'
        //             }
        //             dir('servidor') {
        //                 // Construir imagen Docker para el servidor (Node con MongoDB)
        //                 bat 'docker build -t tu_usuario/servidor .'
        //                 bat 'docker push tu_usuario/servidor'
        //             }
        //         }
        //     }
        // }

        stage('Desplegar Proyecto') {
            steps {
                script {
                    // Comando para desplegar el proyecto (puedes personalizarlo)
                    echo 'Proyecto desplegado'
                }
            }
        }
    }
}
