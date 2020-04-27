//Variables Declaration

def muleversion="4.2.2"
def env="DEV"
def bussgrp="Speridian"
def uri="https://anypoint.mulesoft.com"
def worktype="MICRO"
def worker=1
def branchName = "${env.BRANCH_NAME}"
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
   if(branchName == 'dev'){

   steps{
      // Run the maven build
    
         bat 'mvn clean test'
    
	      bat 'mvn clean install -DskipTests=true'
	  }
	  } 
	  
	  
      }
  }
  }
