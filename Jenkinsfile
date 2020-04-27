//Variables Declaration

def muleversion="4.2.2"
def env="DEV"
def bussgrp="Speridian"
def uri="https://anypoint.mulesoft.com"
def worktype="MICRO"
def worker=1
//def branchName = "${env.BRANCH_NAME}"
// if(branchName == 'dev'){
//   ...
// }
//def mvnHome = tool 'Maven'
def branchName= "${GIT_BRANCH}"

pipeline {
  agent any
     tools {
        maven 'Maven'
        }
  stages {
 
   stage('DEV') {


      when { branch 'dev' }
   steps{
      // Run the maven build
    // echo 'Pulling...' + env.BRANCH_NAME
       echo "${GIT_BRANCH}"
         bat 'mvn clean test'
    
	      bat 'mvn clean install -DskipTests=true'
	  }
	  }  
	   stage('Master') {


      when { branch 'master' }
   steps{
      // Run the maven build
    // echo 'Pulling...' + env.BRANCH_NAME
       echo "${GIT_BRANCH}"
         bat 'mvn clean test'
    
	      bat 'mvn clean install -DskipTests=true'
	  }
	  }  
	  
      }
  }
