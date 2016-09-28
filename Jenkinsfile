node {
    
  stage 'Checkout'

  git 'https://github.com/Cox-Automotive/jenkins-docker-python-example.git'
        
  stage 'Package Docker image'

  def img = docker.build('coxauto/jenkins-docker-python-example:latest', '.')

  stage 'Publish'
  docker.withRegistry('https://nexus.coxautodev.com', 'nexus-admin') {
     img.push('latest')
  }

}
