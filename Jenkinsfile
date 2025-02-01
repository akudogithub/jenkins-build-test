pipeline{
	agent any
		stages{
			stage('git-clone'){
				steps{
					sh ''
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
