# How to Host a Resume
The purpose of this project is to describe how I hosted my resume on Github Pages using VS Code for the editor and Jekyll for the website itself. It also serves to teach anyone from scratch how to host their own resume - the Getting Started section will describe the steps I used. The reason for setting up the publishing pipeline this way is because it allows me to easily update the resume and the website will automatically be updated. This process makes it very easy to make changes, including other contributors, which is why Etter recommended this approach. 

Pipeline: Etter

# Getting Started

### Prerequisites

    - A resume formatted in Markdown
    - Basic knowledge of how to use Markdown
    - A computer running Windows 10 or later

### Installing
To create and host the resume, the following tools need to be installed first. 

I've chosen to use VS Code because Etter recommends using a light-weight Markdown editor. VS Code is light-weight and easy to use including running commands on the command line. 

1. Install VS Code 
    1. [Click](https://apps.microsoft.com/detail/xp9khm4bk9fz7q?launch=true&mode=full&hl=en-us&gl=ca&ocid=bingwebsearch) to download VS Code
    2. Click Install 

In order to run Jekyll we need to download and install Ruby first. 

2. Install Ruby
    1. [Click](https://rubyinstaller.org/downloads/) to download RubyInstaller
    2. Select the latest Ruby+Devkit installer
    3. Double click downloaded file to install
    4. Open VS Code
    5. Press ```Ctrl + ~``` to open the command line terminal
    6. Run ```ruby --version``` to confirm Ruby is installed


3. Install Jekyll
    1. On the command line just opened type ```gem install jekyll bundler``` to install Jekyll
    2. Run ```gem update --system``` to get the latest version

### Create Jekyll Project to Host Resume
Before creating a Jekyll project, we also need a Github account and setup github in VS Code. 
1. [Click](https://github.com/?OCID=AIDcmmcwpj1e5v_SEM__k_1b9bebd486bc1224ad988e0b12043a7a_k_&ef_id=_k_1b9bebd486bc1224ad988e0b12043a7a_k_) to create GitHub Account
2. Setup GitHub in VS Code
    1. Open VS Code
    2. Click on the Extensions tab, likely on the left hand side in the middle area
    3. Install the ```GitHub Pull Requests``` extension

We are now ready to create the project    

3. Create Jekyll Project
    1. Click on the top left Icon that looks like 2 files
    2. Press the open folder button
    3. Create a folder called ```HostResume```
    4. Press ```Ctrl + ~``` if command line is not visible in VS Code
    5. Use ```jekyll new --skip-bundle .``` to create new project

Now that the project is created we want to use github pages so we need to change a few more things in the ```Gemfile``` file

4. Open the ```Gemfile``` file
    1. Add # to the start of the line that starts with ```gem "jekyll"```
    2. Remove # from the start of the line that starts with ```gem "github-pages"``` to use github-pages 
    4. Open ```_config.yml```
    5. Change ```title``` and ```email``` and ```description``` to anything you like
    5. Run ``` bundle install ``` on the command line to install all relevent packages
    6. Run ``` bundle add webrick ```

    Before we can run the website we have to push the changes to github. 

    7. Open the ```Source Control``` icon on the left side
    8. Press ```Publish to GitHub```

    Let's run the website to make sure it works. You should see the default theme ```minima```
    
    9. Run ```bundle exec jekyll server```
    10. Press ```Ctrl``` then click on the server address to view the site

Congratulations! You now have a running local site. Let's link your resume to this site

7. Link resume
    1. Create a folder in this root directory called ```_includes```
    2. Copy your resume into the ```_includes```
    3. Rename resume to ```resume.md```
    4. Open ```index.markdown``` file
    5. Delete the ```layout``` line
    5. Add the following text ```{% include resume.md %}``` below ```---```
    6. Paste the following ```title: Your Name``` above the ```---``` line
    7. Paste the following ```description: Full Stack Developer | City, Province/State ``` below the ```title:``` line
    8. Open ```_config.yml``` and change theme to ```jekyll-theme-cayman```
    9. Open ```Gemfile``` and replace ```minima``` with ```jekyll-theme-cayman```
    10. Replace the theme ```minima``` with ```jekyll-theme-cayman``` and remove all text after on the same line
    11. Delete the ```post``` folder
    12. Delete the ```about.markdown``` file
    13. Run ```bundle install```
    14. Run ```bundle exec jekyll server``` if server is not running
    15. View resume by going to the browser

We now need to go to the respository on Github and setup the project to deploy our website using Github-Pages

9. Setup Github to deploy website
    1. Login to Github
    2. Find project
    3. Go to ```Settings```
    4. Click ```Pages```
    5. Select ```main``` under the branch section
    6. Press ```Save```
    7. Go To ```Actions``` on the tabbar on top
    8. Click the workflow and wait for it to finish
    9. Click on the url underneath the deploy section

Enjoy your hosted resume!

## More Resources
## Authors and Acknowledgements
## FAQs
1. Why is Markdown better than a word processor?
2. Why is my resume not showing up?