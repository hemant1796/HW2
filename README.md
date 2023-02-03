# HW2

---
    output: rmarkdown::github_document
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```
# Homework 2: Data Cleaning

**Due:** Thursday, February 2, 2023 by 11:59pm

**Submitted by : ** Hemant kumar

**UIN** 01243485

The goal of this week's assignment is to gain experience using OpenRefine for data cleaning.

**Note:** This assignment assumes that you have already downloaded and installed [OpenRefine](https://openrefine.org) and worked through the OpenRefine tutorial from Week 2 of CS 625.

## Assignment

Write a report that describes how you carried out the tasks in Part 1 and how you arrived at the answers to the questions in Part 2.

### Report

For this assignment, since you'll just be describing the actions you took using OpenRefine without including R code, you can either directly write in Markdown in `report.md` or your can use R Markdown in `report.Rmd` and the Knit process to generate your `report.md`.
(In any case, `report.md` is the file that I will use for grading.)

I have not provided a template, but I expect your report to include your name, CS625-HW2, date, and appropriate headings and Markdown markup for clarity and neatness.
You will lose points if there are many spelling/grammatical errors or your report is hard to read because of formatting issues.

As for all reports, there should be a "References" section that includes links to any examples that you used in completing this assignment.

### Part 1. Data Cleaning

Create a new project in OpenRefine and load the PetNames.tsv dataset available from <https://github.com/jgolbeck/petnames> (read the README.txt in that repo for more information on the dataset).
If you view the raw version of the data file in GitHub, you can copy that URL directly into OpenRefine to load the data without downloading it separately.

Use OpenRefine to clean the dataset of pet names so that you can answer the questions in Part 2.
Make sure to keep track of all operations you perform.
As much as you can, use OpenRefine facets and GREL transforms to clean the data rather than manual editing (though, some cleaning will need to be done manually).

There are a couple entries where multiple pets are in the same entry.
Make a decision on how to handle these cases and document it in your report.

*Caution:* This is a large, messy dataset.
Clean the data as well as you can, with an eye towards being able to answer the questions in Part 2, but you are not expected to fully clean the entire dataset.

In your report, explain the steps you took to clean the data.
Include screenshots, GREL statements, etc. as needed to clearly document what you did.
If you did any manual cleaning, note that and explain why you did this manually.
Include enough detail so that I am convinced that you understand how to use OpenRefine.

You will likely not have learned everything in class that you need to know to complete the assignment.
I expect that you will watch the tutorials and read documentation, including documentation on the [GREL regex language](https://docs.openrefine.org/manual/expressions#grel-general-refine-expression-language).

When you are done cleaning the file: \* Export the file as a new CSV and save it in your repo as `HW2-petnames.csv`.
\* Extract JSON scripts containing all of the operations you performed on the file and save it in your repo as `HW2-petnames.json`.
(Select **Extract** at the top of the **Undo/Redo** tab. Then copy and paste the JSON script into a new file.)

## Part 1. Data Cleaning

1.  I loaded the PetNames.tsv dataset from the link[**Github link here!**](https://github.com/jgolbeck/petnames)

![a](https://user-images.githubusercontent.com/31125760/216480818-13ae21c7-2c61-41cf-98f3-afe8bfadbb6a.PNG)




2.  On clicking the drop-down under “What kind of pet is this”, from the
    drop-down list click on Facet then click on Text facet then click on
    cluster button on left side of the window pane.

![Screenshot (2)](https://user-images.githubusercontent.com/31125760/216481137-aa27723c-900a-436f-b660-97e9ce450832.png)



3.  The following window will appear after the above step is been
    executed, where there are two methods +Key collision +Nearest
    neighbor I have selected the Key collision method along with
    fingerprint function. Lets see what happen next?

![b](https://user-images.githubusercontent.com/31125760/216481273-89547977-7f93-453a-83d7-c53431ca37ba.PNG)
 You can see that group of pets will appear. Each pet is
having some slight change in their spelling. We will set all the
different spelling of same pet category to same name.

4.  After the above step, we will select key collision method with other
    function i.e metaphone3. You can see that the cluster with
    slightly more changes in the name in same category should appear
    like dog and doggo in our case. So, we will set name and we will
    merge them together by pressing Merge selected & Re-cluster button
    to same cluster. ![image](https://user-images.githubusercontent.com/31125760/216481383-a5c355ba-1fb1-4dba-b748-73045caeb7cd.png)
 Similarly, there are six other
    types of function. which we can perform along with the Key collision
    method.

5.  After this, we will select the nearest neighbor method with
    levenshtein function having radius 1.0 and Block Chars 2.0, you can
    see two different pets i.e cat and god but that is two different
    pets. So, we are not changing any names here.
    ![image](https://user-images.githubusercontent.com/31125760/216481808-7a3c4a69-c6c9-44ee-a177-d771367a6b62.png)
    
6.  We can also change the pet names manually i.e. in our case I have
    changed the bunny to Rabbit, Gecko and Gerbil to Lizard, etc. This
    can be done by clicking on the text facet where you will see two
    option (edit and exclude). click on exclude you will see the
    following image.

    
  ![image](https://user-images.githubusercontent.com/31125760/216482044-c850ec43-d9ed-46bc-ba3f-7ae4ac3262dc.png)



  ![image](https://user-images.githubusercontent.com/31125760/216482141-417625db-7aec-479a-a492-78aabf03b3c8.png)

If you click on edit button, the pop-up will appear to change the name
of the cluster. In which, I have changed the various name to same
category like bunny to Rabbit, Gecko and Gerbil to Lizard, etc as
mentioned above. 



7.  You can also remove the cluster which are not related, you can see
    in the following image I have clicked on Hermit crab, click on All
    column tab then click on edit rows and remove all matching rows.
  ![f](https://user-images.githubusercontent.com/31125760/216474151-c381d716-d23d-455f-b88a-8a24ba9a0756.PNG)  
 After clicking on remove all matching rows the
    following output will appear, where all the related rows is been
    deleted. After this click on exclude button which is shown in orange
    color to apply the changes to clusters in the dataset.


  ![g](https://user-images.githubusercontent.com/31125760/216474191-21f0203d-1651-49d4-87d0-6f9e2a8d0dc9.PNG) 


8.  Now, lets filter Pet’s age column, for that click on facet -&gt;
    Numeric facet. Follwing screen will appear
    
  ![image](https://user-images.githubusercontent.com/31125760/216482369-db41a0da-825c-4b1c-96e1-28cd3bba449a.png)

  After this, click on the drop-down under Pet’s age column, Select Edit
    cells -&gt; Transform. The following screen will appear where you
    can write the GREL query in order to get the desired output.
    The query in the above screenshot, where it removes
    the sub-string years. after this, click ok buttom on the left side
    of pop-up to apply the changes.
  ![i](https://user-images.githubusercontent.com/31125760/216474279-67bb4325-b182-4dad-99ba-acb338561bf4.PNG)
    

9.  You can see in the following screenshot that after removing the
sub-string from the Pet’s age column, It is converted to
number after going to Pet’s age column
drop-down then select Edit cells -&gt; Common transforms -&gt; To
number. This will convert all the string data to Numeric value in the
column.


![j](https://user-images.githubusercontent.com/31125760/216474393-5f11e8d0-7a18-4b69-b910-7281d9394d3f.PNG)





You can see that now the Pet’s age consists of Numeric value. you can
see the green color in the Pet’s age column which represents the numeric
values.


10. Finally you can now see that the data is now cleaned after applying
    certain filters. ![k](https://user-images.githubusercontent.com/31125760/216474375-e9d8edc5-1455-421e-85f5-67fb5eafb3e4.PNG)

### Part 2. Analyze Cleaned Data

Use the cleaned data to answer the following questions in your report (and explain how you arrived at the answers)

Question : How many types (kinds) of pets are there?

Answer : There are Total 34 Kind of Pets

![1](https://user-images.githubusercontent.com/31125760/215925045-3ab8083e-7128-4f7a-a394-1d2e4cc4a664.png)


Question :  How many dogs?

Answer : There are 1128 dogs.

![2](https://user-images.githubusercontent.com/31125760/215925158-802b4808-0f16-41f7-8a94-a581070c583d.PNG)


Question : How many breeds of dogs?

Answer : There are 320 breeds of dogs

![3](https://user-images.githubusercontent.com/31125760/215927030-f182c0d0-a425-492b-94c1-77e95d901d00.PNG)


Question : What's the most popular dog breed?

Answer : Labrador is most popular breed with 174 as count

![4](https://user-images.githubusercontent.com/31125760/215927231-db7b8a0a-f09c-43d4-b889-c4c81a093ec2.PNG)


Question : What's the age range of the dogs?

Answer : Age range for dogs is 0-21

![5](https://user-images.githubusercontent.com/31125760/215927610-5b1c3174-af51-4a77-bed6-8851df73b1b1.PNG)


Question : What's the age range of the guinea pigs?

Answer :  The age range for Guinea pigs is 1-5

![6](https://user-images.githubusercontent.com/31125760/215928416-f9bb053c-064c-441b-8882-34d0f092f760.PNG)


Question : What is the oldest pet?

Answer : Cat Named Bruce Springsteen is oldest with age 24.

![7](https://user-images.githubusercontent.com/31125760/215930297-6edf655d-1f0e-4d02-9040-20c859ab5393.PNG)



Question : Which are more popular, betta fish or goldfish? How many of each?

Answer : Goldfish are more popular, Goldfish with count 8, and betta fish with count 3

![88](https://user-images.githubusercontent.com/31125760/215933089-c375808d-5e3a-4f8e-9658-598c5762c4bb.PNG)

![8](https://user-images.githubusercontent.com/31125760/215933101-dfe87542-a92d-4d12-85f2-65cd0f871484.PNG)



Question : What's the most popular everyday name for a cat?

Answer : Kitty with 5 count is most popular among cats.

![9](https://user-images.githubusercontent.com/31125760/215933125-30511068-c93d-406d-9e2a-cf76184feaf8.PNG)


Question : What's the most popular full name for a dog?

Answer : Maggie with count of 7 is most Popular among dogs.

![10](https://user-images.githubusercontent.com/31125760/215933144-80a36b38-24c9-4119-9571-ecbb99bfe0aa.PNG)




*I do not expect everyone to have the exact same answers. Some of these will depend upon decisions you make while cleaning the data. Make sure to note any cleaning decisions you made that could have an impact on your answers.*

## Submission

Your GitHub repository should contain the following files (in addition to any assignment files that were provided): \* `report.md` - your report \* `HW2-petnames.csv` - cleaned CSV \* `HW2-petnames.json` - operations used to clean the data in JSON format

Submit the URL of your report (*not the URL of your repo*) in Canvas.
Make sure that you have committed and pushed your local repo to GitHub.
Include "Ready to grade @Faryaneh @saumyadabhi" in your final commit message.

-   Click on HW2 under Week 2 in Canvas
-   Under "Assignment Submission", click the "Write Submission" button.
-   Copy/paste the URL of your `report.md` file into the edit box (should be something like https<nolink>://github.com/odu-cs625-datavis/fall22-hw2-*username*/blob/master/report.md)
-   Make sure to "Submit" your assignment.
