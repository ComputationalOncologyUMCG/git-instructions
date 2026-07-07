Linking Github to Gitlab for admins
===================================

If you want to use the issue tracker and planning of GitLab, with a repository on GitHub, you can link your GitHub repository to GitLab.

.. _create_gitlab_repository:
Step 1: Create GitLab repository
--------------------------------

Visit the `GitLab <https://gitlab.com/>`_ webpage 
Go to the 'Groups' and select 'ComputationOncologyUMCG'

.. image:: images/gitlab_linking_for_admins/go_to_groups.png
   :alt: go_to_groups
   :width: 80%

Then create a new project using 'Create project'

.. image:: images/gitlab_linking_for_admins/create_project.png
   :alt: create_project
   :width: 80%

Create a blank project

.. image:: images/gitlab_linking_for_admins/create_blank.png
   :alt: create_blank
   :width: 80%

Use the same 'project name' and 'project slug' that you also used on github, to make things clear.
Make sure you uncheck all of the 'Project Configuration' boxes.
Then click 'Create project'

.. image:: images/gitlab_linking_for_admins/create_project_button.png
   :alt: create_project_button
   :width: 80%

Next go to 'Settings', 'Access tokens'

.. image:: images/gitlab_linking_for_admins/select_access_tokens.png
   :alt: select_access_tokens
   :width: 50%

Then 'Add new token'

.. image:: images/gitlab_linking_for_admins/add_new_token.png
   :alt: select_access_tokens
   :width: 80%

Here we'll create a token. Naming should follow the GL\_\[applicationname]_FORWARD_TOKEN_T[nthtoken]. So for this example, it would be 'GH_GITINSTRUCTIONS_FORWARD_TOKEN_T1'

Set a description that states this token is used for forwarding.

Use the maximum expiration data, as that is a year.

Set the 'Maintainer' role

check the boxes for: 

- read_repository
- write_repository

Then 'Create project access token'

.. image:: images/gitlab_linking_for_admins/configure_token.png
   :alt: configure_token
   :width: 80%

The token will be created. Keep this tab open, as you won't be able to get the token again.

Finally, double-check your username, as we'll also need that for authentication. It will be what is after the '@'

.. image:: images/gitlab_linking_for_admins/get_username.png
   :alt: get_username
   :width: 80%

.. _add_gitlab_secrets:
Step 2: Add GitLab secrets
--------------------------

Now go back to GitHub, and go to the github repository you are trying to manage on GitLab. There, go to 'Settings':

.. image:: images/gitlab_linking_for_admins/go_to_gh_settings.png
   :alt: get_username
   :width: 80%

Then we'll goto 'Secrets and variables', then 'Actions'

.. image:: images/github_dockerhub_automation/to_secrets.png
   :alt: to_secrets
   :width: 80%

We will add the username and token as secrets. This way they can be used for authentication, without other people being able to see their actual contents. 
Click 'New repository secret'

.. image:: images/github_dockerhub_automation/click_new_secret.png
   :alt: click_new_secret
   :width: 80%

First, we'll add the GitLab user as a secret. We should name this as this GH\_\[applicationname]_FORWARD_USER. So here it would be GH_GITINSTRUCTIONS_FORWARD_USER

.. image:: images/gitlab_linking_for_admins/add_gl_user.png
   :alt: add_gl_user
   :width: 80%

You'll then see the secret being added.

.. image:: images/gitlab_linking_for_admins/see_secret_result.png
   :alt: see_secret_result
   :width: 80%

Next, we'll need to add a secret for the token we generated before. Use the same name you used when creating the gitlab token, and copy the token from GitLab.

.. image:: images/gitlab_linking_for_admins/add_gl_token.png
   :alt: add_gl_token
   :width: 80%


TO BE CONTINUED
