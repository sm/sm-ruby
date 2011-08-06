# BDSM Rails Extension

The Rails extension is used to manage all aspects of a Ruby/Rails
application project deployment as a user.

For example, if the project name is 'todo' then for deployment
you would typically create an 'todo' user on the server with
home directory of /home/todo.

An example walkthrough of using BDSM Rails extension in conjunction
with other extensions (below) to manage an application deployment.

    root# bdsm install rails deploy unicorn nginx

    todo$ bdsm bdsmrc
    todo$ vim ~/.bdsmrc # Adjust any settings necessary, set repo url.
    todo$ bdsm rails setup
    todo$ vim ~/shared/config/database.yml # Tune your database.
    todo$ bdsm deploy # Deploy the applicatoin using the 'deploy' ext.
    todo$ cd ~/current
    todo$ gem install bundler && bundle install # If you swing that way.
    todo$ bdsm unicorn install
    todo$ bdsm rails console
    todo$ bdsm unicorn start # If console loaded properly, start er up!

    root# bdsm nginx install
    root# bdsm nginx server todo


