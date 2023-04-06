** Install docker on your pc **


## Steps

1. In terminal window cd to ./websites.
2. Execute: __git clone git@bitbucket.org:EXAMPLE/EXAMPLE.git__
4. *Clone any other (php) repo here*
5. Make sure to add new .conf files for new repo/sites under ./nginx/conf.d
   6. Use .test as TLD for new hosts
5. run docker-compose up -d
5. Execute __docker exec -it docker-php /bin/sh__
6. Make sure to do composer install, npm run build, etc. for the just cloned repo's.
7. Add __127.0.0.1	public-api.test (etc)__ to your hosts file.
---