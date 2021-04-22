# mayang
mayang

git checkout --orphan gh-pages
git reset --hard
git commit --allow-empty -m "Orphan init"
git checkout main
git worktree add new-gh-pages gh-pages
pushd new-gh-pages
cp -r ../webroot/* .  
cp ../.gitignore .
git add --all
git commit -m "update"
git push -f origin gh-pages
popd
git worktree remove new-gh-pages
git branch -D gh-pages

git checkout main
git pull
git branch -D gh-pages
git checkout gh-pages
