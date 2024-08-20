## Submitting Assignments

This page will explain the steps for submitting assignments for this Android class using Git source control on Github.

### Setup

For this course, you need a [Github account](https://github.com/) which is free to signup. Github is an excellent version control system that makes sharing and collaborating on code as easy as possible. We will be submitting all assignments using GitHub and sharing all our code through GitHub. 

If you do not have a Github account, [sign up here](https://github.com/signup/free) and then you begin creating [free repositories](https://github.com/new). Create a new repository for each project you want to push to GitHub.

### Pushing Code

If you have a project to submit that you have been working, first create a [new public repository](https://github.com/new) and then give it a name associated with the project (i.e AndroidTipCalculator). Once you have this repository, you can commit your files to the repository by finding the repository url which looks like `git@github.com:myusername/reponame.git` but for your project. You can see github's [official guide to creating a repo](https://help.github.com/articles/create-a-repo) as well.

To push your code, simply initialize your git repository and then hook up the repository to your project:

```
$ git status
```

If the repository **is not setup**, then create the git repository with:

```
$ git init
```

**Setup a [.gitignore](https://gist.githubusercontent.com/nesquena/5617544/raw/.gitignore) in the root of the directory** which prevents certain files from being committed.

```
$ touch .gitignore  
(...fill in .gitignore with contents in the link above...)
```

Next, if there's **already an origin**, you can remove it with:

```
$ git remote  
$ git remote rm origin
```

Next, you want to add the remote repository for your Github repo:

```
$ git remote add origin git@github.com:myusername/reponame.git
```

You can now add the files to git using the SourceTree client or why typing:

```
$ git add .
$ git commit -am "Initial commit"
```

and now go ahead and push the code to Github with:

```
$ git push origin master
```

You can also use your favorite Git GUI (for example [SourceTree](http://www.sourcetreeapp.com/)) to do a lot of this process as well.

### Creating the Project README

In your project repository, add a file named **README.md **at the root. **Required elements to include** in the **README** for the project ([see example](https://github.com/codepath/android-rottentomatoes-demo/blob/submission/README.md)):

- How many hours did it take to complete?
- Which required and optional stories have you completed?
- GIF walkthrough of all required and optional stories (using [LiceCap](http://www.cockos.com/licecap/))

Please note that you need to [download LiceCap](http://www.cockos.com/licecap/) and you **MUST include a GIF walkthrough of all required and optional stories** in the README such as:

<img src="https://github.com/codepath/android-rottentomatoes-demo/raw/submission/anim_rotten_tomatoes.gif" alt="" width="300">

Consider **optionally** adding to README:

- Installation instructions
- A description of the project
- Add a LICENSE to the repository
- Add a acknowledging the open-source libraries used

See an example of the [required elements of the README](https://github.com/codepath/android-rottentomatoes-demo/blob/submission/README.md).

### Submitting Through Course System

Once you have **completed all required user stories and added a README as described above** then you are ready to notify us that you are ready for an instructor review, go to the "Assignment Tab" for the project and click the "Submit" button on the right-hand side:

<img src="http://i.imgur.com/sZUa9qY.png" width="600" />

In the dialog that appears, enter the required information about your project:

<img src="http://i.imgur.com/YIrCgau.png" width="400" />

Then press "Submit" at the bottom to finalize your submission. Note that **you can always update your submission at any time** in case you want to re-upload the GIF or update the hours spent.

**NOTE:** If you recorded your app walkthrough as a video file instead of a GIF then please use LiceCap to record a preview of the full video included in the project README.

### Git References

Additional references for Git:

- [Official Git Tutorial](http://git-scm.com/docs/gittutorial)
- [Tensory's HowToGit](https://github.com/tensory/HowToGit/blob/master/README.md)
