# Trifera fork of create-react-app 

This fork is done so that we have custom react-scripts and don't have to eject trifera-web app that was created using create-react-app.
The main purpose of this fork is to add support for flavors (e.g. default vs. customer-specific theme).

This repo needs to be synced to upstream every once in a while using the process described here:
https://help.github.com/en/articles/syncing-a-fork

Basically,

# upstream is set to https://github.com/facebook/create-react-app.git
git fetch upstream
git checkout master
git merge upstream/master
git push origin master
git checkout custom-react-scripts
git rebase master
# edit packages/react-scripts/package.json to bump version number, e.g. "2.1.8-trifera-2.2", git add/git commit
git push --force origin custom-react-scripts

Then, publish to npmjs.org:

cd packages/react-scripts
npm publish --access public

The package will then show up here:
https://www.npmjs.com/package/@evgeny-trifera/react-scripts

and trifera-web will be able to pull it from there (don't forget to update trifera-web's package.json with the new version).