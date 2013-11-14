Careful with what you include in source control
------------

People starting to use source control will usually include everything on the project folder. It's important to take notice of things that shouldn't be under source control.

* **Compiled Sources**

    If you're using statically-typed languages such as .NET or Java, your project will be compiled into a .dll file on folders such as `obj`and `bin`. 

    These files should not be included in source control, as they are binary files that cannot be compared or compressed, and in turn will be sent completely everytime you push to your repository, taking longer to upload and wasting storage space. 

* **Package files** 

    If you use nuget, rvm, nvm, or other package management software to install your project dependencies, your don't need to include them under source control. You just need to include the configuartion file (such as repositories.config, package.json, or gemfile)

* **User-side configuration files**

    Many IDEs add environment configuration files on the project's root folder. If you check-in these files you will have constant conflicts with your teammates who may have different settings.

If you use SVN there's an ignore list where you can add individual files or directories, you could also use expressions to ignore files with an specific extension. 
For a .NET application your list might look like this: *.o *.lo *.la #*# .*.rej *.rej .*~ *~ .#* .DS_Store thumbs.db Thumbs.db *.bak *.class *.exe *.dll *.mine *.obj *.ncb *.lib *.log *.idb *.pdb *.ilk *.msi* .res *.pch *.suo *.exp *.*~ *.~* ~*.* cvs CVS .CVS .cvs release Release debug Debug ignore Ignore bin Bin obj Obj Generated Logs *.csproj.user *.user

If you use git there's [a file called .gitignore](http://git-scm.com/docs/gitignore) that helps you define which files and folders shouldn't be included under source control. 

Github has a public repository of commonly used .gitignore files: https://github.com/github/gitignore