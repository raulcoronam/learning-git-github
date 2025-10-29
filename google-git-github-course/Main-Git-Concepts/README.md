Git Directory

The Git directory, located within the .git folder, serves as a database for your project, storing all the information about the repository, including its history and configuration.
It contains various files and directories that Git uses to track changes, and users typically interact with these through Git commands rather than directly.

Working Tree
The working tree represents the current state of your project, where you can view and modify files. It acts as a workspace for making changes before they are tracked by Git.
This area includes all files that are currently tracked by Git, as well as any new files that have not yet been added to the version control system.

Staging Area
The staging area, also known as the index, is a temporary space where changes are prepared before being committed to the Git directory.
To add files to the staging area, you use the git add command, which indicates which changes will be included in the next commit, allowing for selective version control.

Importancia de un portafolio: 
Los portafolios de GitHub dan a las empresas una idea de los proyectos en los que has trabajado y del tipo de código que puedes escribir.  

¿Qué hacen las personas cuando no conocen sobre control de versiones? 
Usualmente la manera primitiva de hacerlo era que cada miembro del equipo guardaba unna copia del documento, sea para mandarle su parte a los demás miembros del equipo, o para mantener un registro del documento que ya funcionaba pero que se le quieren hacer cambios que no se sabe si puedan ser considerados como errores en el futuro. Sin embargo, esto termina siendo conflictivo cuando todos los miembros del equipo hacen estas acciones, ya que no se mantiene un orden ni un registro de quién hizo qué, cuándo, cómo y por qué. 

Git Structure

Git consists of three main sections: the Git directory (which stores the history of files and changes), the working tree (the current state of the project), and the staging area (where changes are prepared for the next commit).
Each commit in Git creates a snapshot of the project at a specific moment, allowing users to track the history of their work.

File States in Git
Files can be either tracked (part of the snapshots) or untracked (not yet included in snapshots). Tracked files can be in one of three states: modified, staged, or committed.
A modified file has unsaved changes, a staged file is ready to be committed, and a committed file is saved in the Git directory.

Workflow Example
The workflow involves modifying files in the working tree, staging those changes, and then committing them to create a new snapshot.
Commands like git status, git add, and git commit are used to manage these states and track changes effectively.

The course content focuses on the basic workflow of using Git for version control.

Understanding Git Repository

A Git repository consists of a Git directory, a working tree, and a staging area.
Files can be in three states: modified, staged, and committed.
Basic Git Commands

To initialize a repository, use the git init command in a directory.
Use git config -l to check configuration settings, especially user.email and user.name.
Tracking and Committing Changes

New files start as untracked; use git add to track them.
Commit changes with git commit, which records a snapshot of the code with a message.
Modifying Existing Files

After modifying a file, check its status with git status.
Stage changes with git add and commit them using git commit -m for a message.
Practice and Familiarization

Familiarity with these commands comes from practice; try them out to gain confidence.
Upcoming content will cover writing useful commit messages.

Main Git Concepts

Key Git Commands

git init: Initializes a new Git repository in the current directory.
git config -l: Displays the current configuration settings, including user information.
git add: Stages changes to files, moving them from untracked to staged status.
git commit: Records a snapshot of the staged changes in the repository. Use git commit -m "message" to add a commit message directly.
git status: Shows the current status of files in the repository, indicating which are modified, staged, or untracked.

Relevant Linux Commands

mkdir: Creates a new directory.
cd: Changes the current directory to the specified path.
chmod: Changes the permissions of a file, making it executable.
nano: Opens a text editor in the terminal for editing files.
