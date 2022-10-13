def gv

pipeline {
    agent any

    parameters{
        string(name: 'VERSION', defaultValue: '', description: '')

    }

    stages {
        stage("init") {
            steps {
                script {
                    gv = load "script.groovy"
                }
            }
        }
        stage("build jar") {
            steps {
                script {
                    echo "building jar"
                    //gv.buildJar()
                }
            }
        }
        stage("build image") {
            steps {
                script {
                    echo "building image"
                    //gv.buildImage()
                }
            }
        }

        stage("test"){
            when {
                expression{ env.GIT_BRANCH == "test-branch"  }
            }
            steps{ 
                echo 'running tests on test-branch'
                
            }      
        }

        stage("deploy") {
            steps {
                script {
                    echo "deploying"
                    //gv.deployApp()
                }
            }
        }
    }   
}