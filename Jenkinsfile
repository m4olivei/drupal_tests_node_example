pipeline {
  agent none
  stages {
    stage('drupal') {
      agent {
        docker {
          image 'andrewberry/drupal_tests:0.2.0'
        }
      }
      steps {
        sh '''#!/bin/bash

./test.sh node'''
      }
    }
    stage('mariadb') {
      agent {
        environtment {
          MYSQL_ALLOW_EMPTY_PASSWORD = 1
        }
        docker {
          image 'mariadb:10.3'
        }
      }
    }
  }
}
