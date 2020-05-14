# Deploy New Changes

### Adding New Package

Just push your commit to `build-base` branch, and a GitLab job will start building the image which contains the new packages \(Python/NPM\).

Then you can push again the same commit to staging or production environment.

### Staging

Simply, push your commit to `develop` branch, **and the build will automatically start on GitLab.**

### Production

1. Push your commit to `master` branch.
2. Start the build manually from GitLab Jobs \(**after you make sure everything works fine** 🙏\).





