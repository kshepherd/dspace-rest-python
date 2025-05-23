# Maintenance instructions

These notes are for maintenance of the Git / PyPI source and releases / versions, rather than the installed client libraries - if you are not a maintainer, you can skip this doc!

## Release tasks

All the tasks we need to do, in order, when releasing a new version:

1. **Check the main branch!** - we should have all the changes we want to include merged/picked and tested
2. **Update version number** - edit `dspace_rest_client/__init__.py` and update the version. Usually, this will just be a case of incrementing the version number, e.g. `0.1.9` -> `0.1.10`.
3. **Update CHANGELOG.md** - new versions go at the top of the file. See previous release blocks for formatting. I include a 'thanks' or 'reported by' attribution for PRs contributed or issues reported. The new version number is used for the heading and the (future) PyPI URL
4. **Commit release preparation** - once you are happy with the steps above, commit with a message like 'Prepare release 0.1.10'
5. **Push branch** - making sure github is up to date, (in future: CI)
6. **Clear out build and dist directories**: OPTIONAL, but nice to start with a clean Python build environment before making this new version
7. **Run publish script** - with version number as an argument, e.g. `./publish.sh 0.1.10`. This will run `setup.py` to build a new version then upload to PyPI with twine - you will need an API token and publish access in PyPI to do this.
