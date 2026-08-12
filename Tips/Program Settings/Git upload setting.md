Using SSH, Two accounts.

1.  git add .

2. Initial Commit
	git commit -m "Initial commit"

3. Set as main branch
	 git branch -M main

4. Set URL by the github account you want
	Hyungmin-L
		ssh -T git@github.com
		git remote set-url origin git@github.com:Hyungmin-L/<Repository name>.git
	
	Lim-ited
		ssh -T git@github-limited
		git remote set-url origin git@github-limited:Lim-ited/<Repository name>.git

5. Status Check
git remote -v

6. Push
git push -u origin main

7. Contributors
him030107@gmail.com

This is mobile backup Test.