pipeline {
    agent any
    triggers {
        pollSCM '* * * * *'
    }
    stages {
        stage('Build') {
            steps {
                git url: 'https://github.com/cyrille-leclerc/multi-module-maven-project'
                withMaven {
                    chmod +x ./gradlew
                    sh './gradlew assemble'
                }
            }
        }
        stage('Test') {
            steps {
                git url: 'https://github.com/cyrille-leclerc/multi-module-maven-project'
                withMaven {
                    chmod +x ./gradlew
                    sh './gradlew test'
                }
            }
        }
    }
}
