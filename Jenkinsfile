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
        echo env.BRANCH_NAME
        if (env.BRANCH_NAME == 'master') {
            try {
                input message: 'Deploy this build?', ok: 'Publish' 
                echo 'deployed'
            } catch (err) {
                echo 'not deployed' 
            }
        }
    } 
}
