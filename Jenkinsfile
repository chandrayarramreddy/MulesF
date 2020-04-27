//Variables Declaration

def muleversion="4.2.2"
def bussgrp="Speridian"
def uri="https://anypoint.mulesoft.com"
def worktype="MICRO"
def worker=1

pipeline {
  agent any
     tools {
        maven 'Maven'
        }
  stages {
 
   stage('DEV Build') {
 
    when { branch 'dev' }
   steps{
      // Run the maven build
    echo "Building the DEV"
  //  bat 'mvn clean test'    
	  }
	  }  
	  
    stage('DEV Install') {
	
	 when { branch 'dev' }
      steps {
       echo "DEV Installing"
      // bat 'mvn clean install -DskipTests=true'
    
      }
    }
    stage('DEV Deploy') {
	
	 when { branch 'dev' }
	
	//Anypoint Platform Credentails
	 environment {
        ANYPOINT_CREDENTIALS = credentials('muleapi')
      }
      steps {
	  echo "DEV Deploying Application to Anypoint"
        // bat "mvn package deploy -Dmuleversion=${muleversion} -Dusername=${ANYPOINT_CREDENTIALS_USR} -Dpassword=${ANYPOINT_CREDENTIALS_PSW} -Denv=DEV -Dbussgrp='${bussgrp}' -Duri=${uri} -Dworktype=${worktype} -Dworker=${worker} -DmuleDeploy"
   
       }   
     }
	 
	  stage('QA Build') {
 
    when { branch 'QA' }
   steps{
      // Run the maven build
    echo "QA Building the Test"
   // bat 'mvn clean test'    
	  }
	  }  
	  
    stage('QA Install') {

	 when { branch 'QA' }
      steps {
       echo "QA Installing"
    //   bat 'mvn clean install -DskipTests=true'
    
      }
    }
    stage('QA Deploy') {
	
	 when { branch 'QA' }
	
	//Anypoint Platform Credentails
	 environment {
        ANYPOINT_CREDENTIALS = credentials('muleapi')
      }
      steps {
	  echo "Deploying Application to QA"
    //  bat "mvn package deploy -Dmuleversion=${muleversion} -Dusername=${ANYPOINT_CREDENTIALS_USR} -Dpassword=${ANYPOINT_CREDENTIALS_PSW} -Denv=QA -Dbussgrp='${bussgrp}' -Duri=${uri} -Dworktype=${worktype} -Dworker=${worker} -DmuleDeploy"
   
       }   
     }
	 
	  stage('SIT Build') {
 
    when { branch 'SIT' }
   steps{
      // Run the maven build
    echo "Building the SIT"
   // bat 'mvn clean test'    
	  }
	  }  
	  
    stage('SIT Install') {

	 when { branch 'SIT' }
      steps {
       echo "SIT Installing"
     //  bat 'mvn clean install -DskipTests=true'
    
      }
    }
    stage('SIT Deploy') {
	
	 when { branch 'SIT' }
	
	//Anypoint Platform Credentails
	 environment {
        ANYPOINT_CREDENTIALS = credentials('muleapi')
      }
      steps {
	  echo "Deploying Application to SIT"
    //  bat "mvn package deploy -Dmuleversion=${muleversion} -Dusername=${ANYPOINT_CREDENTIALS_USR} -Dpassword=${ANYPOINT_CREDENTIALS_PSW} -Denv=SIT -Dbussgrp='${bussgrp}' -Duri=${uri} -Dworktype=${worktype} -Dworker=${worker} -DmuleDeploy"
   
       }   
     }	 
	 
	 
	 stage('PROD Build') {
 
    when { branch 'PROD' }
   steps{
      // Run the maven build
    echo "Building the PROD"
   // bat 'mvn clean test'    
	  }
	  }  
	  
    stage('PROD Install') {

	 when { branch 'PROD' }
      steps {
       echo "PROD Installing"
     //  bat 'mvn clean install -DskipTests=true'
    
      }
    }
    stage('PROD Deploy') {
	
	 when { branch 'PROD' }
	
	//Anypoint Platform Credentails
	 environment {
        ANYPOINT_CREDENTIALS = credentials('muleapi')
      }
      steps {
	  echo "Deploying Application to PROD"
    //  bat "mvn package deploy -Dmuleversion=${muleversion} -Dusername=${ANYPOINT_CREDENTIALS_USR} -Dpassword=${ANYPOINT_CREDENTIALS_PSW} -Denv=PROD -Dbussgrp='${bussgrp}' -Duri=${uri} -Dworktype=${worktype} -Dworker=${worker} -DmuleDeploy"
   
       }   
     }	 
	 
	 
	 
    }
  }
