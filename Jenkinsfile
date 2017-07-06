pipeline {
    agent any
    stages {
        stage('build mem-nginx'){
            steps {
                openshiftBuild(bldCfg: 'mem-nginx', showBuildLogs: 'true')
            }
        }
        stage('tag mem-nginx'){
            steps {
                openshiftTag(srcStream: 'mem-nginx', srcTag: 'latest', destStream: 'mem-nginx', destTag: 'dev')
            }
        }
    }
}