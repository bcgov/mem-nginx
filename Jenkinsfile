pipeline {
    agent any
    stages {
        stage('build rproxy'){
            steps {
                openshiftBuild(bldCfg: 'rproxy', showBuildLogs: 'true')
            }
        }
        stage('tag rproxy'){
            steps {
                openshiftTag(srcStream: 'rproxy', srcTag: 'latest', destStream: 'rproxy', destTag: 'dev')
            }
        }
    }
}

