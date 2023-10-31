# Nicola's Portfolio Website

## About Me 
Born and raised in Italy, I moved to the UK in 2015. I have always been interested in new technologies and IT, as I studied IT in my A levels back in Italy. After 5 years working in content management for a website, I decided to make the step of learning Front-End Development thanks to the edX course, and on this page I want to showcase not only my progress as a student but also a journey that hopefully will lead to new exciting projects in this field.

## Usage

You can visit the Horiseon website by clicking [HERE](https://nikola84ca.github.io/my-portfolio/). There you can navigate though the website using the top navication links that will redirect you to the relative portion of the website.

## Installation
First, make sure that Git and Git Bash are installed on your system. To download this project on your machine click [HERE](https://github.com/Nikola84ca/my-portfolio) to go to the repository on GitHub. Click on the green CODE botton, and copy the link of the repository. In your machine, open gitBash and create a new folder where you will clone the project using the command below

```bash
Git mkdir your-project-folder
```
navigate inside the new folder, and clone the project files with the following comands

```bash
cd your-project-folder
Git clone url-copied-on-repository
git pull
```

Open your editor with the command

```bash
code .
```

alternatively download the zip file in GitHub after pressing the Code button, unzip it and copy it in your project folder. Navigate to the folder using the cd command on gitbash and lounch your editor as shown above with code .

## Website Description 

The website is a single page that consists of these elements, listed from top to bottom.

* An Header where we find my name and includes three links pointing to specific sections of the page, and an external link.
* A big background image, the hero banner with a specific headline.
* An About Me section, containing a small picture of me and a short intro/bio.
* A Work section, where I highlight the latest project with a big picture, and four more project sit below. All picture of the project have a nice hover effect that remove the overlay color once hovering with the mouse. All project sections have a title and description, and the title works as a link to the specific webpage of the relative project.
* A simple Contact Me section with phone number, email, gitHub profile and website.

Here is an example of the functionality implemented in the header links; when clicked they direct the user to the relative section of the main article.

![Gif animation of the header links, when clicked they will redirect the user to the relative sections of the webpage](/css/readme-assets/portfolio-desktop-view.gif)

As you can see, the titles of the section occupy the 20% at the right of the screen, leaving the remaining space for the content.

## My Process

* The first thing I did was designing a clear structure of containers to have a clear idea of how to organize all the content. I started creating a dinamic navigation bar, followed by a large section containing a background gif and an h2 for the headline "Coding to make a difference".

* For each content section I opted for a flex structure, where a main section contains the relative title and another container which contains the picture and bio for the about me section, a structure of articles for the work section, and a simple link list for the contact section. This made it easy to assign a left border to those section, and make the design clear and tidy. 

Here is an example of the HTML structure and its Relative CSS styling code:

```HTML
<section class="contactSection">
        <h2 id="contactTitle">Contact Me</h2>
        <div id="contactList">
        <ul>
        <li><p id="phoneNum">Phone: +44074734734 </p>
        </li>
        <li>
      <a id="emailAdd" href="mailto:nico@websitewow.com"> Email </a>
      </li>
      <li>
        <a id="gitHub" href="https://github.com/Nikola84ca"> GitHub </a>
        </li>
        <li>
          <a id="webSite" href="https://github.com/Nikola84ca"> Website </a>
          </li>
      </ul>
      </div>
    </section>
```

```CSS
.contactSection {
 color: var(--darkCol);
  display: flex;
  flex-wrap: wrap;
  height: 75px;
  justify-content: space-around;
  align-items: center;
  align-content: center;
  margin-top: 200px;
}

.contactSection a {
color: var(--darkCol);
}

#contactList {
  display: flex;
  justify-content: space-between;
  border-left-style: solid;
  width: 70%;
  flex-grow: 2;
  margin-left: 20px;
}

```
* Another feature I implemented is the overlay color and hover effect with the mouse. 

![Gif animation of the projects section, when passing the mouse on them the overlay color fades, and the background picture is fully visible.](/css/readme-assets/projects-hover-effect.gif)

Here is my approach to this task, speficically on the section of the Project 1:

```CSS

#project1 {
  object-fit: contain;
  height: 320px;
  width: 900px;
  background-image: url(images/02-portfolio-1.jpg);
  background-size: cover;
  position: relative;
  margin-left: 100px;
  
  
}
#project1::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5); 
  opacity: 1;
  transition: opacity 0.3s ease; /* This adds a transition for smooth visibility change */
  pointer-events: none; /* this line ensures the overlay doesn't interfere with mouse events */
}

#project1:hover::before {
  opacity: 0; /* When hovering, the overlay becomes transparent */
}

```

* I made sure that the website is responsive for mobile view, it still needs some fixing for tablets and other sizes screens but this is how the content is organized on mobile:

![Gif animation of the mobile view of the website.](/css/readme-assets/portfolio-mobile-view.gif)

The content is align in colums and all the functionality of links and hover effects are working. This is my CSS approach to achieve that, specifically on the projects section:

```CSS

@media screen and (max-width: 900px) {

  h1 {
    font-size: 15px;
  } 


  .workSection {
    flex-direction: column;
    align-items: center;
  }

  
  #project1 {
    object-fit: contain;
    height: 320px;
    width: 320px;
    margin-left: 17px;
    background-size: cover;
    position: relative;
      
    
  }
  #project2 {
    height: 120px;
    width: 414px;
    margin-left: 17px;
    margin-top: 10px;
    background-size: cover;
    }

    #project2::before {
     width: 318px;
    }

}

```

## Credits

I would like to thank all the teachers and TA of the EdX bootcamp for all the content provided. I would like to credit [w3 schools](https://www.w3schools.com/html/html5_semantic_elements.asp) for the useful content about HTML semantic elements.

## Project Status and Upcoming Improvements

Although the website is optimized for desktop view and mobile view, it is still not responsive for tablet and other screen sizes. The next steps to offer a more accessible and performant user experience is to work on the CSS of the website in order to make the website even more responsive and easy to navigate on all other devices as well. A new design, using a Grid structure will be a possible approach to this next step.

## Collaborations and Contributions

I welcome all the brilliant coders out there to join me in this project. Join effort can result in a fundamental learning experience for a beginner coder like me, so feel free to reach out with tips and advice. If you want to contribute to this project, pull requests are welcome, but if you want to make major changes, please open an issue first so that we can discuss what you would like to change. You can contact me on my GitHub profile [HERE](https://github.com/Nikola84ca) and visit this project repository by clicking [HERE](https://github.com/Nikola84ca/my-portfolio).

[![Contributor Covenant](https://img.shields.io/badge/Contributor%20Covenant-2.1-4baaaa.svg)](code_of_conduct.md)

## License

[MIT](https://choosealicense.com/licenses/mit/)