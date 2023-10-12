---
layout: post
title:  How and Why You Should Personalize Your Mac Terminal
date: 2023-10-11 21:30:00
description: Make your CLI experience more enjoyable with these tips and tricks.
tags: links code
categories: How-To
thumbnail: assets/img/terminal.jpg
---
<!-- <a href="https://en.wikipedia.org/wiki/Cold-pressed_juice">cold-pressed</a> -->

Enter the world of data science, and you'll soon realize that your computer's Terminal isn't just a tool; it's a gateway to an uncharted realm of power and productivity. For over a year, I've been on a quest to uncover the secrets and unlock the potential of the Command Line Interface (CLI) and the journey has been nothing short of transformative. The CLI isn't just a sea of obscure text—it's a realm of power, capable of reshaping the way you work and interact with your data. From mastering Git for version control to effortlessly renaming mountains of files, from scripting automation tasks to setting up databases and managing packages, the CLI has been my trusty companion. Yet, amidst all the triumphs, one can't help but notice the challenges—the daunting uniformity of text and the the disorienting sensation of navigating your directories.

Over the last year I've learned a lot and made just a couple quick edits that have completely changed both my efficiency with and enjoyment from using the CLI. I've perused parts of the <a href="https://www.gnu.org/software/bash/manual/bash.html">Bash Reference Manual</a> and scoured a lot of Stack Overflow discussions to find solutions to my problems. 

For anyone learning Data Science/Analytics, I hope this helps!


## Disclaimer: Bash v. Zsh 

If you're using your Mac's Terminal, you've probably noticed the default shell is Zsh. As with anything related to computers and code, the Bash v. Zsh debate can be pretty intense at times even though <a href="https://www.geeksforgeeks.org/bash-scripting-difference-between-zsh-and-bash/">they're very similar shells</a>.  When I was first learning the CLI in my <a href="https://catalog.byu.edu/courses/14178-000">Data Science Ecosystems</a> class at BYU, my instructor used Bash so I followed his example. I honestly haven't looked too far into the differences between the two shells, but I haven't run into any issues with making Bash my default shell. 

All examples given below assume that Bash is the default and suggest all readers follow along.

To switch the default shell to Bash, run the following command and then enter your password as prompted.
```
chsh -s /bin/bash
``` 

## Part 1: Customizing Your Bash Prompt

I prefer using a dark theme for my terminal so I've edited my basic profile by clicking "Terminal" in the top left corner of the screen near the Apple logo. The following path through the settings may be helpful: Terminal > Settings > Profiles > Text (tab). Under the "Text" tab, I changed the background color to be Black, the Text and Bold Text to be white, and changed the cursor to be an underline that blinks (see red arrows below).

None of these changes is required, but if you want to follow along with the tutorial, these changes should help our results look similar. 

<div class="row justify-content-md-center">
    <div class="col-lg-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/terminalProfileSettings.jpg" title="Terminal Settings" class="img-fluid rounded z-depth-1" %}
    </div>
</div>


### Step 1: Display Username as Prompt

As shown below, my prompt is “Aarons-MacBook-Pro-65: ~ aoustrich$” which is the name of my machine with some extra details (not sure what the 65 is for) followed by a colon, the folder I’m in (~ means the root folder), and then finally my username with a $ at the end. 


<div class="row justify-content-md-center">
    <div class="col-lg-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/defaultBash.jpg" title="Default Bash" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

This is a very long prompt and doesn't really give us much information to help us navigate the CLI.

We can simplify this prompt to only include our username in just a few easy steps, but first we need to understand the `.bash_profile` a little better.

You can think of the .bash_profile as a sort of settings or configuration file for your terminal. Running the command `nano .bash_profile` from the root (~) directory, we can open up the file to check out our settings. Depending on what software you have used so far, your `.bash_profile` will either be empty (i.e. just created by the nano command) or it will have some information already in it. Mine already had some things set up for conda and different paths for different versions of Python. 

Whether or not your `.bash_profile` is empty, create a new section called "Custom Terminal Prompt" by using the # as a comment character. Add the following lines to this section:

```
# Custom Terminal Prompt

export CLICOLOR=1
PS1="\[\e[1;91m\]\u\[e[m\]:" 
PS1+=">> "
export PS1;
```

The `export CLICOLOR=1` line tells the terminal to use different colors than what has been set up in the Prodile. `PS1` is string we'll be building to become our new prompt. Setting `PS1="\[\e[1;91m\]\u\[e[m\]:"` involves finding the username with the "\u" and the rest of the code controls the way the username is formatted. In this example, we display the username in bold red text (See the LSCOLORS section of  <a href="https://gist.github.com/thomd/7667642">thomd's repo</a> for more information on how the colors work). We set `PS1+=">> "` to add on two greater than symbols after the username so we can more easily see the end of our prompt. The last line `export PS1;` tells the terminal to use the new prompt. 


#### Save the `.bash_profile` and "Refresh" Your Terminal

To save changes to the `.bash_profile` in the nano editor, enter the following commands:` control + x`, `y`, and then `enter/return`. 

Changes made to the `.bash_profile` are not immediately displayed in the terminal because the current window is following the old instructions. To "refresh" your terminal and see the new changes, run the following command (or simply open a new window of the terminal).

```
source ~/.bash_profile
```

Your terminal should now look something like this.

<div class="row justify-content-md-center">
    <div class="col-lg-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/addUsername.jpg" title="Username" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

### Step 2: Add Current Working Directory to the Prompt

Our new prompt can be made more useful if we displayed our current working directory since it's easy to get lost in all the folders we may have in our project. 

Add new lines to the "Custom Terminal Prompt" section of your `.bash_profile` so it looks like this:
```
# Custom Terminal Prompt

export CLICOLOR=1
PS1="\[\e[1;91m\]\u\[e[m\]:" 
PS1+=" "
PS1+=”\[\e[1;96m\]\W\[e[m\] ”
PS1+=">> "
export PS1;
```

Similar to the line that formats the "\u" username, this new line `PS1+=”\[\e[1;96m\]\W\[e[m\] "` prints our current directory in bold turquoise text.

Save the changes to the `.bash_profile` and "Refresh" your terminal to see your current directory in the prompt. It's easiest to see this updated propmpt if you change directories like this:

<div class="row justify-content-md-center">
    <div class="col-lg-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/addDirectory.jpg" title="Add Directory" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

### Step 3: Show the Current Branch of a Git Repo

When working with Git and Github, it's easy to confuse which branch you're making edits and committing changes on. To make our lives easier, let's add our current branch to our prompt.

Add new lines to the "Custom Terminal Prompt" section of your `.bash_profile` so it looks like this:

```
# Custom Terminal Prompt

export CLICOLOR=1

# Function to get Git branch
git_branch() {git branch 2>/dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/’ }

PS1="\[\e[1;91m\]\u\[e[m\]:" 
PS1+=" "
PS1+=”\[\e[1;96m\]\W\[e[m\] ”
PS1+=" "
PS1+=”\[\e[0;92m\]\$(git_branch)\[e[m\]”
PS1+=">> "
export PS1;
```

After saving and "Refreshing" our `.bash_profile`, our terminal prompt should now show what branch we are working on in light purple text. (Note: If we are not in an initialized git repo, nothing will show up.)

<div class="row justify-content-md-center">
    <div class="col-lg-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/addBranch.jpg" title="Add Branch" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

## Part 2: Making the `ls` Command Easier to Read

By default, running `ls` shows the items in a current directory, but it doesn’t tell us much about what each item is. If I’m working in a directory I haven’t used in a while or if I’ve cloned someone else’s repository from GitHub, it can be pretty difficult to know what’s going on in the directory and I might accidentally try to "cd" into a text file that doesn’t have the ‘.txt' extension.

Solution: Change the `.bash_profile` to customize how different items will be displayed by the `ls` command. Use this <a href="https://geoff.greer.fm/lscolors/">tool</a> to customize your `ls` results.

Add new lines to the "Custom Terminal Prompt" section of your `.bash_profile` so it looks like this:

```
# Custom Terminal Prompt

export CLICOLOR=1

# Function to get Git branch
git_branch() {git branch 2>/dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/’ }

PS1="\[\e[1;91m\]\u\[e[m\]:" 
PS1+=" "
PS1+=”\[\e[1;96m\]\W\[e[m\] ”
PS1+=" "
PS1+=”\[\e[0;92m\]\$(git_branch)\[e[m\]”
PS1+=">> "
export PS1;

# Export LS Colors
export LSCOLORS=XefxcxdxXDegedabagacad 
```

After saving and "Refreshing" our `.bash_profile`, our terminal should now show directories with a blue background and executable files with a brown background. 

<div class="row justify-content-md-center">
    <div class="col-lg-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/lsColors.jpg" title="Custom ls" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

## Part 3: Extra Tips

- It’s annoying to see the “Last login: “ message when opening up a new session of the Terminal. You can get rid of this by running `touch .hushlogin` at the root level.

- Add “export BASH_SILENCE_DEPRECATION_WARNING=1” to the `.bash_profile` to get rid of the “default interactive shell is Zsh” message shown in new windows.

If both these steps are completed, it should look like this when you open a new terminal window:

<div class="row justify-content-md-center">
    <div class="col-lg-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/cleanStart.jpg" title="Clean Start" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

## Final Thoughts

One of the most empowering things about the journey to learn Data Science/Analytics is how many things you learn along the way that allow you to customize your workflow. 

I encourage you to follow the steps I've given to make your learning journey just a little bit more efficient and enjoyable by personalizing your Mac Terminal. Experiment with different ways of formatting the various parts of the `PS1` prompt and do what makes life easier for you! 

And when you find a prompt that works for your needs, let me know what it looks like!

As always...

Enjoy your Adventures in Analytics!