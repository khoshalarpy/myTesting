#!groovy

pipeline {
    agent {
        node {
            label 'master'
        }
    }
    parameters {
        choice(
            name: 'ReleaseScope',
            choices: "minor\npatch\nMajor",
            description: 'Release type' )
    }

    stages {
         stage('Integration Tests') {
              steps {
                    //echo "Creating RC branch from " + env.BRANCH_NAME
                    echo "release scope is ${params.ReleaseScope}"
                    sh "echo testing"

              }
        }
   }

}