---
title: "Python Course"
collection: teaching
type: "Python Begginer to Intermediate Course materials and tasks for my students."
permalink: /teaching/Python
---

I'm Python programmer with strong technical background. I'm using python in my everyday work as a tool for building aplications, webscrapping, artificial intelligence, music and many other interesting stuff. Repository [Python-Course](https://github.com/SaxMan96/Python-Course) is a handy database with all materials and tasks for my students.

# About:
I'm Python programmer with strong technical background, and I like to teach people.  I've created a GitHub repository [Python-Course](https://github.com/SaxMan96/Python-Course) with materials and tasks for my students. I'm using python in my everyday work as a tool for building aplications, webscrapping, artificial intelligence, music and many other interesting stuff. Check out my Begginer to Intermediate Course.

If you want to be my student:

- visit my profile on [E-korepetycje](https://www.e-korepetycje.net/mateuszdorobek)
- write me an email: `dorobekmateusz(at)gmail.com`
- contact me via: [LinkedIn](https://www.linkedin.com/in/mateuszdorobek/) 
- checout my website: [www.mateuszdorobek.pl](https://www.mateuszdorobek.pl)

# Environment

Installation of python environment is way easier when doing it with virtual environment manager such as MiniConda.  For proper installation follow these steps:

1. Install MiniConda from [here ](https://docs.conda.io/en/latest/miniconda.html) (choose version for Python 3.7)

2. After installation press "Win" button and type "Anaconda prompt". In Anaconda command line type:

   ```bash
   $ conda -V
   ```

3. Make  sure that you have the newest version of conda, otherwise, update conda using:

   ```bash
   $ conda update conda
   ```


# Git

Our tutorial requires you to install [GIT](https://git-scm.com/downloads). Select **Git Bash** during installation and use this command line when using GIT. At first use there will be pop up to enter your GitHub login data.

After you install GIT, follow these steps:

0. **Fork** this repo using button at the bottom of [this](https://github.com/SaxMan96/Python-Course) page

1. **Clone** forked repository to your local machine using:

   ```bash
   $ git clone https://github.com/<YOUR_USERNAME>/Python-Course.git
   ```
   
2. **Pull Request** from mine GitHub repo to your fork everytime that I've uploaded new tasks, and then **Pull** the changes to your local machine. Your master needs to be up to date.

   ```bash
   $ git pull origin master
   ```

If you configured your git branch properly, you can start working on tasks. 

1. After you've changed some files you have to add it to your staging area using:

    ```bash
    $ git add [file]  
    ```
    or to add all files
   
    ```bash
    $ git add .
    ```
    
2. When you add all wanted files, you can save added file to your local repository with:

    ```bash
    $ git commit -m "commit message"
    ```
    
3. If you want to send changes to GitHub repository use ```$ git push``` as mentioned above.

4. If you want to start working with new task use ```$ git pull origin master``` command to make sure you have recent version of repository on your local machine.

# Integrated Development Environment - IDE

For our tutorial we will use **Jupyter Notebook** as our IDE, but there are a lot of alternatives such as Pycharm, Spyder, Visual Studio Code etc.

To open Jupyter Notebook file (such as *Introduction.ipynb*):

1. Open Anaconda Prompt, it should look like this:

   ```bash
   (base) C:\Users\John>
   ```

   (base) - means that you have active *base* environment.

2. Go to your file location e.g.:

   ```
   cd C:\Users\John\Desktop\Python-Tutorial
   ```

3. Then type:

   ```
   jupyter notebook
   ```

\* click help tab and learn shortcuts to work with Jupyter faster.

# Lessons

- [**Lesson 1** - Introduction](https://github.com/SaxMan96/Python-Course/blob/master/lessons/Lesson%2001%20-%20Introduction.ipynb)
- [**Lesson 2** - Containers Part I - Lists & Tuples](https://github.com/SaxMan96/Python-Course/blob/master/lessons/Lesson%2002%20-%20Containers%20Part%20I%20-%20Lists%20%26%20Tuples.ipynb)
- [**Lesson 3** - Conditional Instructions & Operators](https://github.com/SaxMan96/Python-Course/blob/master/lessons/Lesson%2003%20-%20Conditional%20Instructions%20%26%20Operators.ipynb)
- [**Lesson 4** - Loops](https://github.com/SaxMan96/Python-Tutorial/blob/master/lessons/Lesson%2004%20-%20Loops.ipynb)
- [**Lesson 5** - Containers Part II - Dictionary & Set](https://github.com/SaxMan96/Python-Tutorial/blob/master/lessons/Lesson%2005%20-%20Containers%20Part%20II%20-%20Dictionary%20%26%20Set.ipynb)
- [**Lesson 6** - String Formatting](https://github.com/SaxMan96/Python-Tutorial/blob/master/lessons/Lesson%2006%20-%20String%20Formatting.ipynb)
- [**Lesson 7** - Functions](https://github.com/SaxMan96/Python-Tutorial/blob/master/lessons/Lesson%2007%20-%20Functions.ipynb)
- [**Lesson 8** - Lambdas](https://github.com/SaxMan96/Python-Tutorial/blob/master/lessons/Lesson%2008%20-%20Lambdas.ipynb)
- [**Lesson 9** - Classes](https://github.com/SaxMan96/Python-Tutorial/blob/master/lessons/Lesson%2009%20-%20Classes.ipynb)
- [**Lesson 10** - Inheritance](https://github.com/SaxMan96/Python-Tutorial/blob/master/lessons/Lesson%2010%20-%20Inheritance.ipynb)

# Sources

- [GIT](https://git-scm.com/downloads) - installation file
- [Miniconda](https://docs.conda.io/en/latest/miniconda.html) - installation file
- [W3Schools](www.w3schools.com/python), [Tutorialspoint](www.tutorialspoint.com/python), [Learnpython](www.learnpython.org)- some of the examples