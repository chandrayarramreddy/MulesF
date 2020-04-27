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

pipeline {
  agent any
     tools {
        maven 'Maven'
        }
  stages {
 
   stage('DEV') {


  //    when { branch '${branchName}' }
   steps{
      // Run the maven build
    // echo 'Pulling...' + env.BRANCH_NAME
       echo 'Pulling...11111 ${env.BRANCH}'
         bat 'mvn clean test'
    
	      bat 'mvn clean install -DskipTests=true'
	  }
	  }  
	  
      }
  }
