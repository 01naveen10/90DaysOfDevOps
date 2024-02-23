1. What’s the difference between continuous integration, continuous delivery, and continuous deployment?
A)
CI : integarte code changes where automated testa are run
CD : automating deploying it to various enviroments like testing production etc
CD : autoamting every change to piepline

2. Benefits of CI/CD
A)
faster production, higher quality software, greater collabiration

3. What is meant by CI-CD?
A) automating devlopment life cycle from code commit to deploying it

4. What is Jenkins Pipeline?
A) it allows set of plugins to  to define CI Cpieline as code using DSL groovy

5. How do you configure the job in Jenkins?
A) select job then type of job, scm build triggers build steps post build etc

6. Where do you find errors in Jenkins?
A) we can find it in build console, logs, build history, pipeline

7. In Jenkins how can you find log files?
A) in build console, build history, archive artifacts

8. Jenkins workflow and write a script for this workflow?
A) jenkins workflow aka pipeline to automate software process
pipeline{
    agent
    stages{
        stage('build'){
            steps{}
        }
    }
}

9. How to create continuous deployment in Jenkins?
A) can use jenkinsfile to write pieline and deploy, after passing tests etc

10. How build job in Jenkins?
A) by using build steps, jenkins configuration  running shell command scripts maven etc

11. Why we use pipeline in Jenkins?
A) to use pipeline as code, reusing functions, visualisation of whole deployment, support parllel execution

12. Is Only Jenkins enough for automation?
A) it is useful for autoamtion but for build test etc we might need other tools and we can use plugins to connect

13. How will you handle secrets?
A) using credentials plugin, environment variables using external manager like hashicorp aws secret maangaer

14. Explain diff stages in CI-CD setup
A) SCM >> build >>test >> artifacts >> deploy >> monitor

15. Name some of the plugins in Jenkin?
A) Git, pipeline, docker ,build, artifacts, github, kubernetes, sonarQube