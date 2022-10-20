node{

    stage('SCM Checkout')
    {
        git credentialsId: 'GITHUB_CRED', url: 'https://github.com/VenkataGKrishna/online-shop-master.git'
    }
    
    stage('Run Docker Compose File')
    {
        sh 'sudo docker-compose build'
        sh 'sudo docker-compose up -d'
    }
  stage('PUSH image to Docker Hub')
    {
       withCredentials([string(credentialsId: 'DOCKER_HUB_CRED', variable: 'dockerhub')]) 
        {
            sh "docker login -u venkata1981 -p ${dockerhub}"
        }
        sh "docker push venkata1981/mysql"
        
        //docker.withRegistry( 'https://registry.hub.docker.com', 'DockerHubPassword' ) {
             
            // sh 'sudo docker login -u "upasanatestdocker" -p "Zephyr@17" docker.io'
             //sh 'sudo docker push upasanatestdocker/mysql'
             //sh 'sudo docker push upasanatestdocker/job1_web1.0'
            // sh 'sudo docker push upasanatestdocker/job1_web2.0'
            // sh 'docker push upasanatestdocker/mysql'
          
    }
}
