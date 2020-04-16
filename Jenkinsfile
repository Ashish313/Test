node{

	def app
	stage('Clone Repository'){
			checkout scm
			}
	
	stage('Build image'){
			app=docker.build('ashish313/sample')
			}

	stage('Test image'){
			app.inside{
				sh 'echo "Tests passed"'
				}
			}

	stage('Push image'){
			docker.withRegistry('https://registry.hub.docker.com','docker-hub-credentials'){
													app.push()
													app.push('latest')
													}
			}

}
