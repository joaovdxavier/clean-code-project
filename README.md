# Applying Clean Code principles to a Dataquest Project
This repo aims to apply some concepts of Clean Code programming given by professor Ivanovitch Silva in the MLOps course at UFRN/IMD and to get a 10/10 score by using pylint. You can find his classes at his [repository]("https://github.com/ivanovitchm/mlops").

## The Project
The project chosen to apply the concepts on is a machine learning python notebook (.ipynb) available at [dataquest/solutions]("https://github.com/dataquestio/solutions/blob/master/Mission155Solutions.ipynb"). 

It contains the solution to one of the courses in the Dataquest platform: Guided Project: Predicting Car Prices.

## What will be done?
In this notebook, we are going to follow these steps:
1. Generate the notebook (.ipynb file) that refers to the guided project.
2. Validate the file generated in step 1 by executing it on Jupyter Lab (Anaconda).
3. Generate a python file (.py) from the notebook.
4. Use pylint on the python file to get a score.
5. Use autopep8 to eliminate some of the errors pointed.
6. Change our code (using clean code principles) so our score can increase.
7. Repeat steps 4 and 6 until we have a 10/10 score.

## What you need 
1. Anaconda - offers the easiest way to perform Python/R data science and machine learning on a single machine (as they say in their [website](https://www.anaconda.com/)). Follow the instructions there to download and install Anaconda on your machine.
2. 

## Starting the Project
### Step 1
We can achieve this step by just clicking on the button available in the "Guided Project: Predicting Car Prices" at [dataquest.io](dataquest.io). After that, we can download the file and put it on our project directory.

### Step 2
Open the Anaconda Navigator, select Jupyter Lab. After that, go to the directory where the .ipynb file is located and execute it.

The file 'imports-85.data' is available at this repository.

If everything is right, the file should run smoothly.

### Step 3
After validating Step 2, let's now use the ```script_before_pylint.py``` file.

### Step 3.5
Return to the Anaconda Navigator main page and go to "Environments" tab. On the right screen, search for  ```pylint``` and ```autopep8```. If they are not in the "installed packages" list, follow the next steps.

1. Open a terminal window on the "New Launcher" button, upper left in the Jupyter Lab webpage.
2. Type ```pip install pylint``` and ```pip install autopep8```, wait for them to finish installing and you're good to go.

### Step 4
Check if the terminal is on the directory you are currently working on before using this command.

```
pylint script_before_pylint.py
```

After a few seconds it gives us our first score... 4.36/10. Ouch! We need to improve this script.

### Step 5
Go back to the terminal screen and type the following command:

```
autopep8 --in-place --aggressive --aggressive script_before_pylint.py
```

We are telling autopep8 to OVERWRITE the file with its changes, so it will correct a lot of stuff and then overwrite our file.

By rerunning the command on Step 4, we got now a 4.29/10 score. Apparently autopep8 did nothing but to disturb.

### Step 6
We wil now try to correct the mistakes pylint showed us. This step is basically reading the command's output and correcting as it tells us.

* A lot of lines have whitespaces, so check out for them. Also, a lot of lines are too long, so try to give breaks between them.
* After fixing up whitespaces, we got now real problems.
* We need to change our functions names in order to stop "redefining" them, so I just put numbers in the end of their names.
* Fixed some names that were not according to snake case.

After lots of cleaning, I was finally able to get a 9.66 score. The only thing left was this warning: 
```script_before_pylint.py:29:15: E1136: Value 'cars' is unsubscriptable (unsubscriptable-object)```

And after a little research I found out that pylint lacks a little bit on this area. After all, our code runs and works, so this warning is kind of annoying.

For the ```numeric_cars = cars[continuous_values_cols]``` line you can use
```
# pylint: disable=unsubscriptable-object 
```

## Conclusion
After some work, I was finally able to say that my code was clean! (According to pylint)

In fact, our code became simpler, more readable and smoother. I was able to remember my classes while I was changing the lines so my code could be clean.

I hope this repository can be useful for people who are trying to learn clean code principles.

The initial and final code are available so you can see the difference.