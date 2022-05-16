pipeline {
  agent {
    docker { image 'liquibase/liquibase:4.4.2' }
  }
  environment {
    MARIADB_CREDS=credentials('mariadb')
  }
  stages {
    stage('Update') {
      steps {
        sh 'liquibase update --url="jdbc:mysql://34.93.86.225:3306/liquibase" --changeLogFile=db-changelog.sql --username=$MARIADB_CREDS_USR --password=$MARIADB_CREDS_PSW'
      }
    }
  }
}