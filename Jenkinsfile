pipeline{
	agent any
		stages{
			stage('git-clone'){
				steps{
					checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'akudogithub', url: 'https://github.com/akudogithub/jenkins-build-test.git']])
				}
			}
			stage('system-resources check'){
				steps{
					lscpu
					date
					free 
				}
			}
			stage('parallel-stage'){
				parallel{
					stage('sub-job-1'){
						steps{
							lsblk
						}
					}
					stage('sub-job-2'){
						steps{
							echo "this is sub-job 2"
						}
					}
				}
			}
			stage('build-stage'){
				steps{
					id jenkins
					free -g
				}
			}
		}
}
