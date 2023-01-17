pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        echo 'Compilando'
      }
    }

    stage('Test') {
      steps {
        input 'Desea ejecutar los test'
      }
    }

    stage('Test unitarios') {
      parallel {
        stage('Test unitarios') {
          steps {
            echo 'los test unitarios son un mojón'
          }
        }

        stage('Test de integración') {
          steps {
            echo 'Ejecutamos los test de integración'
          }
        }

        stage('Test smoke') {
          steps {
            echo 'Ejecutamos los test smoke'
          }
        }

      }
    }

    stage('Checkpoint') {
      steps {
        checkpoint 'Test incompleto'
      }
    }

    stage('Deploy') {
      steps {
        input 'Desea hacer el deploy'
      }
    }

  }
}