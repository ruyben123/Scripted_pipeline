pipeline {
	agent none
	stages{

	stage('Non parallel stage'){
		agent{
					label "master"

					}
		steps{
				echo 'This stage is executed first'
		}
	}

	stage('Run test'){
		parallel{
			stage('test on windows'){
				agent{
					label "l"
				}
				steps{
					echo "task1 on agent"
				}
			}
			stage('test on master'){
				agent{
					label "master"
			}
				steps{
					echo "task1 on master"
				}

			}
		}
	}
	}
}
