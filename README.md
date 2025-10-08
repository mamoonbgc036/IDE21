# IDE21 - Design and develop in the CMS admin panel
<img width="100%" alt="IDE21 25.08, Design and Develop in the CMS admin panel" src="https://github.com/user-attachments/assets/99fcb7e3-cae0-44b0-96d6-5e275cc21f6e" />

Restarting CMS-IDE project from 2013, now powered by Docker, which made the task of installing this software trivial. It needs a fat rewriting, since the technology used in it originally is Zend Framework 1, and now it should be translated to Laravel.

The base idea of the software is to be able to design the website in the admin panel, and do it in visual way, having the CMS in the background which will take care of the functionality, while the front should be 100% customizable right there in the admin panel, and being able to change the looks very quickly to something quite different with a few clicks, but also can add CSS and JS on the fly.

Basically have the designer and the frontend developer in one person, from the admin panel.
After that template is available for export, it can be uploaded to some other installation of IDE21, and the design which was created by the first admin on one domain can now be taken by another admin to work on it to improve it in his own way on another domain, which should enable quick creating of the new templates ( new designs ).
This is the base idea, there are still some bugs and unfinished features, there will be Wiki documentation created for User and Developer realms, which describe what is posible to do, and what is in TODO list.

# FEATURES so far
- Design templates in admin panel
- create pages with the same principle, assign template to be used with the specific page
- TailwindCSS - use classes to create designs
- DaisyUI - use components and themes
- create and display Menus
- create and display Categories
- use Modules ( form creation, user, search)
- upload Images and use them in design
- Multi User: set ACL permissions on the pages
- Multi Language: add as many languages as you want
- Write CSS and/or Javascript if you need to, every user can write his own
- website administration is possible on a mobile device

and more…


# SCREENSHOTS
MOBILE:

<img width="100%" alt="IDE21 25.08, edit templates on mobile" src="https://github.com/user-attachments/assets/b7f48fc8-8562-472a-8830-1d7f7eac2325" />

DESKTOP:

<img width="100%" alt="IDE21 v25.08 Nord theme" src="https://github.com/user-attachments/assets/4843bb5e-0ca9-4bde-b865-2f13623d02a0" />
<img width="100%" alt="IDE21 v25.08 Nord theme - Managing DaisyUI themes" src="https://github.com/user-attachments/assets/708efe6c-4c81-48be-9669-ad2ba3dbf357" />
<img width="100%" alt="IDE21 v25.08 Valentine theme" src="https://github.com/user-attachments/assets/c685f5d9-4dfe-469f-b12d-f24127a0ea86" />
<img width="100%" alt="IDE21 v25.08 Night theme" src="https://github.com/user-attachments/assets/aec580f2-484f-4f72-a37a-d5098e7a5180" />

# YOUTUBE CHANNEL

IDE21 playlist:

https://youtube.com/playlist?list=PL9J82k6JLMCSzktjF3NLeNDEFidb9E6xx&feature=shared


using IDE21 for website administration on a mobile phone:

https://youtu.be/WZEZ3wNYZHg?feature=shared

----------------------------------------------------------------------------------
IDE21 introduction originally streamed on LinkedIn and later published to Youtube, 
40 minutes long, in which Nebojsa Tomic explains editing of the templates


[![IDE21 design directly in your CMS](https://img.youtube.com/vi/FX7hTeB0nc4/0.jpg)](https://www.youtube.com/watch?v=FX7hTeB0nc4)

-----------------------------------------------------------------------------------

# INSTALLATION OF THIS VERSION

- Install Docker
- Clone this repo
- cd to dir
- replace certificates in apache2 folder with your own if you do not want just to try this out; apache2 folder and its contents enables https on localhost
- Run in terminal:

  $ docker compose up

After succesful building and running, you can access the front at https://localhost, and admin area at https://localhost/adm


For locahost/adm :

Demo user:  proba

Demo pass:  proba

*  /adm can be changed to what ever path you want if you modify adminUrl variable inside src/legacy/dev-application/config/config.ini

If you consider further use of IDE21, set your own configuration for the database in docker-compose.yaml, and config files inside dev-application, do not use this default configuration, naturally.

If you want to develop, note that container uses Named volume by default. In order to be able to see your changes in the container instantly ( not rebuild the image ), you should uncomment Host volume and comment the Named volume in docker-compose.yaml:

`#- ./src:/var/www/html # UNCOMMENT this if you want to use Host src folder inside running container - for development use`

`- 'ide21src:/var/www/html' # otherwise use Named volume - for production use`

DO NOT PUSH THE CHANGES YOU MADE IN docker-compose.yaml TO REMOTE BRANCH

# DEMO

https://demo.ide21.com/admin

user: proba

pass: proba

*  upload and mail disabled in this demo
contact me for a fully functional instance


# IF YOU WOULD LIKE TO CONTRIBUTE
This project needs volunteers in the form of designers, frontend developers, backend php developers who are familiar with both Zend and Laravel frameworks, since Todo list will be populated with translating Zend functionality to Laravel in the backend. Also frontend part will be going in the mobile direction where the templates which user can create should be mobile friendly and responsive.
There is a lot to rewrite here, but it should not be impossible to create something new and exciting...

* NOTE that only [verified](https://docs.github.com/en/authentication/managing-commit-signature-verification) commits will be accepted

Any kind of support regarding no-code contributions like sharing on social media, creating posts or videos about using this project, or anything else that comes to mind, is more than welcome.

# Translation

1. Fork this repository
2. Create branch on your fork for translation, for example 'german' branch
3. Create a new file in src/legacy/dev-application/languages/creator/  (if german than de.php - for other languages check what i18n locale you should use)
4. You should see all the strings for creator admin panel in src/legacy/dev-application/languages/creator/en.php, use them for your language.
5. When creating a new translation, there is also a website front part: copy src/legacy/dev-application/languages/en.php - contents of this file to src/legacy/dev-application/languages/YOUR_LANG_CODE.php and translate, and there is a  part that uses javascript files for translating some strings: src/public/js/language/creator/en.js should be copied to src/public/js/language/creator/YOUR_LANG_CODE.js and translated
6.  Commit the changes to your branch on your fork, and create a pull request

**If the language translation for your language already exists, it can have some missing translations, and those are generated in .php.missing file. You can also contribute there, by adding the missing translation strings, in the .php.missing file...**

* NOTE that only [verified](https://docs.github.com/en/authentication/managing-commit-signature-verification) commits will be accepted ( if you edit directly in Github web interface the commits are signed and verified automatically )

Anyone interested in contributing, or need help with installing, running or using it, contact me on [LinkedIn](https://www.linkedin.com/in/nebojsatomic/).
