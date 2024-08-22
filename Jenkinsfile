#!groovy
library "knime-pipeline@main"

properties([
    buildDiscarder(logRotator(numToKeepStr: '5')),
    disableConcurrentBuilds(),
])


try {
    node ('partner-agent'){
        stage('Checkout Sources') {
            checkout scm
        }
        stage('Checkout Sources'){
            knimetools.defaultTychoBuild('org.knime.community.template.update')
        }
    }
} catch (ex) {
    currentBuild.result = 'FAILURE'
    throw ex
}
/* vim: set shiftwidth=4 expandtab smarttab: */
