pipeline {
  agent {
    docker { image 'liquibase/liquibase:4.4.2' }
  }
  stages {
    stage('Test') {
      steps {
      withCredentials([usernamePassword(credentialsId: 'liquibase', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
        sh 'liquibase update --url="jdbc:mysql://34.93.86.225:3306/liquibase" --changeLogFile=db-changelog.sql --username=$USERNAME --password=$PASSWORD'
      }
      }
    }
  }
}