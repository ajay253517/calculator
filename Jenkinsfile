pipeline {
agent { node { label 'docker-java' } } 
stages {
stage("Checkout") {
steps {
git  branch: 'feature-*', url: 'https://github.com/ajay253517/calculator-ci-cd.git'
}
}
stage("Unit Test"){
steps {
sh "./gradlew test"
}
}
stage("RunsOnly"){
steps {
echo "Runs on feature-branch"
}
}
}
}
