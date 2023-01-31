Techn Debts:
- `docker-compose build --no-cache` gets stack. Cannot build new images. Cannot pull new openVRE commits
	- Now, code is manually pulled from front_end container

- Data in /volumes is not properly stored in GIT, ownership is altered. Cannot recreate MongoDB files. To fix it, do not store db_path files, but mongo dumpfiles. Commit them using pre/post-commit hooks:
	- https://stackoverflow.com/questions/3207728/retaining-file-permissions-with-git/3208143#3208143
	- Alternatively DO NOT store data in GIT, but mount /gpfs/ instead of volumes/ + apply backup policy

- Permission error in docker socket solved only manually: `chmod 666 /var/docker/socket.blabla`. Either:
	- Apply the fix in sgecore dockerFile
	- Match host docker group with sgecore docker group. For instance using ARGs in docker build: `docker build --build-arg DOCKER_GID=$(id -g docker) -f Dockerfile -t testing`
	- Instruct the user to apply the fix when installing

- queue name
 
