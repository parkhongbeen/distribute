로컬에서 docker run

1. build
   - poetry export
   - docker build
2. copy secrets
   - docker run (bash)
   - docker cp secrets.json
3. run
   - collectstatic
   - docker run (supervisor)

배포해서 run까지 하려면!?

1. (로컬) build, push
2. (서버) pull, run (bash)
3. (로컬) secrets를 서버로 copy
4. (서버) secrets를 container로 copy
5. (서버) run
   - collectstatic
   - docker run (supervisor)