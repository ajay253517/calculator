pipeline {
agent { node { label 'centos' } } 
stages {
stage("Checkout") {
steps {
git  branch: 'main', url: 'https://github.com/ajay253517/calculator-ci-cd.git'
}
}
stage("Compile"){
steps {
sh "./gradlew compileJava"
}
}
stage("Unit Test"){
steps {
sh "./gradlew test"
}
}
}
}