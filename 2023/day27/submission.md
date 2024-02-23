# Task-01

- Create a docker-integrated Jenkins declarative pipeline
- Use the above-given syntax using `sh` inside the stage block
- You will face errors in case of running a job twice, as the docker container will be already created, so for that do task 2

# Task-02

- Create a docker-integrated Jenkins declarative pipeline using the `docker` groovy syntax inside the stage block.
- You won't face errors, you can Follow [this documentation](https://tempora-mutantur.github.io/jenkins.io/github_pages_test/doc/book/pipeline/docker/)

- Complete your previous projects using this Declarative pipeline approach


A)
use this 
Jenkinsfile (Declarative Pipeline)
pipeline {
    agent {
        docker { 
            image '01naveen10/simple-nodejs-website:latest'
            args '-p 3000:3000'
        }
    }
    stages {
        stage('Deploy') {
            steps {
                sh 'node server.js'
            }
        }
    }
}

instead of this
```groovy
stages {
        stage('Build') {
            steps {
                sh 'docker build -t 01naveen10/simple-nodejs-website:latest'
            }
        }
    }
```

to avoid docker already containing docker image error we use docker stage for it with args -p so that the port mappin gwith ec2 and docker container will be done
also add the files which are requred by the docker file to run in th egit repo so that when jenkins pipeline runs it can fetch those docuents as well