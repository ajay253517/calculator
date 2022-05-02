pipeline {
agent { node { label 'docker-java' } } 
environment {
        BUILD_TAG = sh(script:'date +%F-%H-%m-%S', returnStdout: true)
    }
stages {
stage("Checkout") {
steps {
git  branch: 'feature-*', url: 'https://github.com/ajay253517/calculator-ci-cd.git'
}
}
stage("Unit Test"){
steps {
sh "echo "My variable is ${BUILD_TAG}""
}
}
stage("RunsOnly"){
steps {
echo "Runs on feature-branch"
}
}
}
}
