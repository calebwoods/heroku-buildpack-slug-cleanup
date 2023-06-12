# Heroku Buildpack: app/assets Cleanup

### Delete app/assets and node_modules folder

After assets are precompiled, they are moved to the `public/assets` directory. `app/assets/` and `node_modules/` is not longer required, deleting this frees up space to get around the Heroku slug size limit

## Usage
```bash
$ heroku buildpacks -a barkbox-dev
=== barkbox-dev Buildpack URLs
1. https://github.com/DataDog/heroku-buildpack-datadog.git
2. https://github.com/timshadel/heroku-buildpack-github-netrc.git
3. heroku/nodejs
4. heroku/ruby
```

Add this to the last step.
```bash
$ heroku buildpacks:add --index 5 https://github.com/CloudSecurityAllianceCI/heroku-buildpack-slug-cleanup.git -a barkbox-dev

Buildpack added. Next release on barkbox-dev will use:
  1. https://github.com/DataDog/heroku-buildpack-datadog.git
  2. https://github.com/timshadel/heroku-buildpack-github-netrc.git
  3. heroku/nodejs
  4. heroku/ruby
  5. https://github.com/CloudSecurityAllianceCI/heroku-buildpack-slug-cleanup.git
```
