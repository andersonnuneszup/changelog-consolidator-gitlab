# changelog-consolidator
Project destined to automate the changelog creation in Gitlab plataform.

## Objective
* In order to facilitate the process of documenting project changes, this solution creates a process in which each developer writes a file that documents their change and when generating code consolidation in a main branch, a "gitlab pipeline" is triggered. which consolidates all merged files into one main file that centralizes all changes

## Prerequisites
* It is necessary that the project where this code is hosted on gitlab;
* It is necessary that some project administrator user on gitlab create a variable with the name "CI_TOKEN" in the project that contains the value of a token of a user with permission to write in the repository;
* It is necessary that some project administrator user on gitlab create more two variables with the names are:
	* CI_EMAIL_USER (contains the email of the project administrator user)
	* CI_NAME_USER (contains the name of the project administrator user)
* This variables are used in the gitlab ci to commit and push changes;

## How to use
* Modifications fall into 3 categories:
	* Additions
	* Corrections
	* Improvements
* This division is done in order to facilitate categorization in the consolidated file. Each type of modification will fit into a specific folder.
* The code is configured to commit the changelogs when there is a commit on the "master" branch. It is only in this action that the consolidation takes place, but it is possible to easily modify this behavior if the developer wants to.
* To exemplify, in the case of a developer creating a new functionality. It should create a txt file with the change information.   As a suggestion, we have the text below where the activity code is inserted in the activity management system used, a brief description of the new functionality and the author of the modification: 
	*  User registration entered in the system #289404 - by @andersonnuneszup
* After merging the code in the predetermined branch, an action will be executed that will read all the txts inside the 3 folders allocated inside the "unreleased" folder and insert their text inside the central file called "CHANGELOG.md"
