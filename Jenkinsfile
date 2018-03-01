
stage('checkout intygstjanst') {
    node {
        checkout scm
    }
}

stage('build') {
  node {
            sh 'sbt gatling:test -Dgatling.simulationClass=BasicSimulation'
        }
    }


stage('gatling') {
    node {
            try {
                sh "echo 'gatling archive'"
            } finally {
                gatlingArchive()
            }
        }
    }
