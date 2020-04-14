node{

	def app
	stage('Clone Repository'){
			checkout scm
			}
	
	stage('Build Image'){
			app=docker.build('')
			}

	stage('Test Image'){
			app.inside{
				sh 'echo "Tests passed"'
				}
			}

	stage('Push Image'){
			docker.withRegistry('https://registry.hub.docker.com','docker.hub.credentials'){
													app.push()
													app.push('latest')
													}
			}

}
