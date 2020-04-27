//Variables Declaration

def muleversion="4.2.2"
//def env="PROD"
def bussgrp="Speridian"
def uri="https://anypoint.mulesoft.com"
def worktype="MICRO"
def worker=1
//def mvnHome = tool 'Maven'

pipeline {
  agent any
     tools {
        maven 'Maven'
        }
  stages {
 
   stage('Build') {
  // echo "Building DEV Environment"
    when { branch 'dev' }
   steps{
      // Run the maven build
    echo "Working D Build"
       //  bat 'mvn clean test'    
	  }
	  }  
	  
    stage('Install') {
	//echo "Building DEV Environment"
	 when { branch 'dev' }
      steps {
       echo "Working D Install"
       //  bat 'mvn clean install -DskipTests=true'
    
      }
    }
    stage('Deploy') {
	//echo "Building DEV Environment"
	 when { branch 'dev' }
	
	//Anypoint Platform Credentails
	 environment {
        ANYPOINT_CREDENTIALS = credentials('muleapi')
      }
      steps {
	  echo "Working D Deploy"
        // bat "mvn package deploy -Dmuleversion=${muleversion} -Dusername=${ANYPOINT_CREDENTIALS_USR} -Dpassword=${ANYPOINT_CREDENTIALS_PSW} -Denv=${env} -Dbussgrp='${bussgrp}' -Duri=${uri} -Dworktype=${worktype} -Dworker=${worker} -DmuleDeploy"
   
       }   
     }
	 
	  stage('MBuild') {
 //  echo "Building DEV Environment"
    when { branch 'master' }
   steps{
      // Run the maven build
    echo "Working M Build"
       //  bat 'mvn clean test'    
	  }
	  }  
	  
    stage('MInstall') {
	//echo "Building DEV Environment"
	 when { branch 'master' }
      steps {
       echo "Working M Install"
        // bat 'mvn clean install -DskipTests=true'
    
      }
    }
    stage('MDeploy') {
	//echo "Building DEV Environment"
	 when { branch 'master' }
	
	//Anypoint Platform Credentails
	 environment {
        ANYPOINT_CREDENTIALS = credentials('muleapi')
      }
      steps {
	  echo "Working M Deploy"
        // bat "mvn package deploy -Dmuleversion=${muleversion} -Dusername=${ANYPOINT_CREDENTIALS_USR} -Dpassword=${ANYPOINT_CREDENTIALS_PSW} -Denv=${env} -Dbussgrp='${bussgrp}' -Duri=${uri} -Dworktype=${worktype} -Dworker=${worker} -DmuleDeploy"
   
       }   
     }
	 
	 
	 
	 
	 
    }
  }
