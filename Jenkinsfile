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

//    environment {
//        JAVA_HOME = '/usr/lib/jvm/java-1.8.0-openjdk-1.8.0.242.b08-0.amzn2.0.1.x86_64'
//    }

    stages {
         stage('Nebula testing') {
              steps {
                    //echo "Creating RC branch from " + env.BRANCH_NAME
                    echo "release scope is ${params.ReleaseScope}"
                   sh "chmod +x gradlew"
                  sh "git checkout 0.1.0"
                  sh "./gradlew candidate -PrelScope=${params.ReleaseScope}"

              }
        }
   }

}