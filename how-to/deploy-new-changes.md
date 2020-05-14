# Deploy New Changes

### Adding New Package

Just push your commit to `build-base` branch, and a GitLab job will start building the image which contains the new packages \(Python/NPM\).

Then you can push again the same commit to staging or production environment.

### Staging

Simply, push your commit to `develop` branch, **and the build will automatically start on GitLab.**

### Production

1. Push your commit to `master` branch.
2. Start the build manually from GitLab Jobs \(**after you make sure everything works fine** 🙏\).

### Database Migration

1. Connect to the server using ssh \(or aws eb tool\).
2. `sudo docker ps` to list all containers.
3. `sudo docker exec CONTAINER_ID /bin/sh` to go inside the backend container.
4.  `python manage.py migrate` to start the migration.

