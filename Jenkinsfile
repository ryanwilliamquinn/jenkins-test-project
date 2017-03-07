stage('build') {
    node {
        sh 'whoami'
        sh 'npm --version'
        sh 'npm install'
        checkout scm 
    }
}

stage('test') {
    node {
        sh 'npm test'
    }
}

stage('deploy') {
    node {
        if (BRANCH_NAME == 'master') {
            try {
                input message: 'Deploy this build?', ok: 'Publish' 
                echo 'deployed'
            } catch (err) {
                echo 'not deployed' 
            }
        }
    } 
}
