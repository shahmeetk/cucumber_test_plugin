#!/usr/bin/env groovy
@Library(['eng-build-utils']) _

pipeline{
	agent {
		node {
			label 'placeable-sicm'
		}
	}
    stages {
		stage('Build') {
			steps {
				//run your build
					dir ('dotfiles/') {
						git (
							url: 'git@github.com:shahmeetk/cucumber_test_plugin.git',
							credentialsId: 'github-access',
							branch: 'master'
													//branch: 'feature/PLACEABLE-8000_geocoder_google'
						)
						sh 'ls -la'
					}
			   
				
			}
			post {
				always {
					//generate cucumber reports
					dir('dotfiles/') {
					sh 'ls -la'
					cucumber '**/*.json'
					
					}
				}
			}
		}
	}	
}
