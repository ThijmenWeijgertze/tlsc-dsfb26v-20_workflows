# Reproducible Research {#represintro}


This lesson is about the 'movement' in science called 'Reproducible Research'. It explains the principles of Open Science and connected terms such as Open Access, Open Source and Reproducible Research, Open Peer Review and Open Data. You will practice with workflows that enable working reproducible.

## Before you start! 
A reminder of the exercise and assignment directives.

Within the lesson you will encounter a number of exercises. 

Please answer all the assignments and exercises in an RMarkdown document. You learned how to make one in DAUR1. Save it somewhere in your **course project**. 

**This lesson has two portfolio assignments!**
Save those as separate .Rmd files in a **portfolio-project**.

<div class="tip">
So, you will have at least 3 R projects (file --> new project...) going on this semester: one for all the regular exercises in the lessons. One for your portfolio. A third one for projecticum. 

We suggest to call them:

 1. `dsfb2_workflows_exercises`
 2. `dsfb2_workflows_portfolio`
 3. `dsfb2_research_project`
 
**Start by setting these projects up in your RStudio environment (server or local)**  

Once you are done doing this, you are ready to start this course!

</div>







## Introducing Reproducible Research

This fragment is adapted from [this book](https://book.fosteropenscience.eu/en/02OpenScienceBasics/04ReproducibleResearchAndDataAnalysis.html)

Reproducibility means that research data and code are made available so that others are able to reach the same results as claimed in scientific outputs. Closely related is the concept of replicability, the act of repeating a scientific methodology to reach similar conclusions. These concepts are core elements of empirical research. Thus far, the focus in your education has been on the replicability principle. In order to increase the quality of your research output, we now turn our focus to reproducibility in this course.

Improving reproducibility leads to increased rigour and quality of scientific outputs, and thus to greater trust in science. There has been a growing need and willingness to expose research workflows from initiation of a project and data collection right through to the interpretation and reporting of results. These developments have come with their own sets of challenges, including designing integrated research workflows that can be adopted by collaborators while maintaining high standards of integrity.

The concept of reproducibility is directly applied to the scientific method, the cornerstone of Science, and particularly to the following five steps:

 - Formulating a hypothesis
 - Designing the study
 - Running the study and collecting the data
 - Analyzing the data
 - Reporting the study

Each of these steps should be clearly reported by providing clear and open documentation, and thus making the study transparent and reproducible. Many factors can contribute to the causes of non-reproducibility, but can also drive the implementation of specific measures to address these causes. The culture and environment in which research takes place is an important 'top-down' factor. From a 'bottom-up perspective, continuing education and training for researchers can raise awareness and disseminate good practice. This is the central reason why we adress this issue and provide you with the tools to do reproducible research in this course

While understanding the full range of factors that contribute to reproducibility is important, it can also be hard to break down these factors into steps that can immediately be adopted into an existing research program and immediately improve its reproducibility. One of the first steps to take is to assess the current state of affairs, and to track improvement as steps are taken to increase reproducibility even more. 

![Some of the common issues with research reproducibility are shown here.](https://book.fosteropenscience.eu/en/Images/image_2.png){ width=60%}

[Click for Source: Symposium report, October 2015. Reproducibility and reliability of biomedical research: improving research  practice](https://acmedsci.ac.uk/viewFile/56314e40aac61.pdf)

### Open Science

Open Science is the practice of science in such a way that others can collaborate and contribute, where research data, lab notes and other research processes are freely available, under terms that enable reuse, redistribution and reproduction of the research and its underlying data and methods (FOSTER Open Science Definition). In a nutshell, Open Science is transparent and accessible knowledge that is shared and developed through collaborative networks (Vicente-Sáez & Martínez-Fuentes 2018).

Open Science is about increased rigour, accountability, and reproducibility for research. It is based on the principles of inclusion, fairness, equity, and sharing, and ultimately seeks to change the way research is done, who is involved and how it is valued. It aims to make research more open to participation, review/refutation, improvement and (re)use for the world to benefit.

### Why do we need Reproducible (Open) Science?

 >- To assess validity of science and methods we need access to data, methods and conclusions
 >- To learn from choices other researchers made
 >- To learn from omissions, mistakes or errors
 >- To prevent publication bias (also negative results will be available in reproducible research)
 >- To be able to re-use and/or synthesize data (from many and diverse sources)
 >- To have access to it all!
 
If you think this is really cool and want to know a lot more, here is the <p style="font-size:14px">[Nature Collection on this topic](https://www.nature.com/collections/prbfkwmwvz)</p>
 
### The _GUI problem_

Most people would agree that this seems to be a good practice. Let's all do open science! However, many people use GUI based software (graphical user interface). Citing Wikipedia, this is a *"user interface that allows users to interact with electronic devices through graphical icons and audio indicator such as primary notation, instead of text-based user interfaces, typed command labels or text navigation."* So basically, any program that you use by clicking around in menu's, or using voice control etc, for data science this could for instance be SPSS (you used it in BID-dataverwerking) or Excel.

However, how would you 'describe' the steps of an analysis or creation of a graph when you use GUI based software? 

![](/home/chris.vanoevelen/workflows/tlsc-dsfb26v-20_workflows/images/messy_steps.jpg)<!-- -->

<p style="font-size:14px">**The file "./Rmd/steps_to_graph_from_excel_file.html" shows you how to do this using the programming language R.</p>

Maybe ~~videotape~~ tiktok-record your process and add .mp4 to your paper? Type out every step in a Word document? Both options seem rather silly. This is actually really hard!

**"In fact, you can only do this sensibly using code, so it is (basically) impossible in GUI based software"**

### What you need for replication

To replicate a scientific study we need at least:

- **Context** Scientific context! Research questions, related publications.. [<mark>P<mark/>]
- **Methods** Exactly how the data was gathered [<mark>P</mark>, _D_, <mark>C</mark>]
    + In what model or population? (e.g. some cell line, some knockout mouse etc)
    + *Exact* (experimental) design of the study
- **Data** Actually the raw data itself, to check if you find something similar [<mark>D</mark>] 
- **Meta data** which is data about the data. For instance who gathered it, when, where, licence information, keywords...)[<mark>D</mark>, _C_] 
- **Data analysis** All steps in data analysis [_P_, <mark>C</mark>]
    + Exploratory data analysis of the data 
    + data mangling decisisons, such as fitering and outlier selection
    + Which inductive statistical tests or inference was done and how.
- **Interpretation** How the data was interpreted [<mark>P</mark>, _C_]
    + All choices made in the interpretation of the data (there is usually not one possible way to interpret results..)
    + Conclusions and academic scoping of the results
- **Access to all of the above!** [<mark>OAcc, OSrc</mark>]

<p style="font-size:14px">$P = Publication$, $D = Data$, $C = Code$, $OAcc = Open\ Access$, $OSrc = Open\ Source$ </p>

So we can conclude that:

$Reproducible\ (Open)\ Science = P + D + C + OAcc + OSrc$

<!--  > - Scientific context, research questions and state of the art [<mark>P<mark/>] -->
<!--  > - (Experimental) model or characteristics of population or matter studied [<mark>P</mark>] -->
<!--  > - Data that was generated and corresponding meta data [<mark>D</mark>, _C_] -->
<!--  > - **Exact** (experimental) design of the study [<mark>P</mark>, _D_, <mark>C</mark>] -->
<!--  > - Exploratory data analysis of the data [_P_, <mark>C</mark>] -->
<!--  > - **Exact** methods that were used to conduct any formal inference [_P_, <mark>C</mark>] -->
<!--  > - Model diagnostics [_C_] -->
<!--  > - Interpretations of the (statistical) model results/model fitting process [_P_, _C_] -->
<!--  > - Conclusions and academic scoping of the results [<mark>P</mark>, _C_] -->
<!--  > - **Access to all of the above** [<mark>OAcc, OSrc</mark>] -->

<!-- <p style="font-size:14px">$P = Publication$, $D = Data$, $C = Code$, $OAcc = Open\ Access$, $OSrc = Open\ Source$ </p>  -->

<!-- So we can conclude that  -->

<!-- $Reproducible\ (Open)\ Science = P + D + C + OAcc + OSrc$ -->
<!-- and  -->

### Hydroxychloroquine example

Is (hydroxy)chloroquine really an option for treating COVID-19?
As you probably know, hydroxychloroquine was repeatedly touted as a promising cure for COVID-19 by US President Donald Trump in 2020. 

<img src="/home/chris.vanoevelen/workflows/tlsc-dsfb26v-20_workflows/images/trump_chloroquine.png" width="680" />

<p style="font-size:14px">https://www.washingtonpost.com/politics/2020/04/07/trumps-promotion-hydroxychloroquine-is-almost-certainly-about-politics-not-profits/</p>

But how are we really doing with (hydroxy)chloroquine as a treatment for COVID-19?
We know by now that treating COVID-19 with hydroxycholoroquine is not an option. There is no scientific proof that it helps in reducing the severity of the disease. But back at the start of the pandemic in 2020, things were not so clear. If anything, it could worsen the outcome of the disease. It has severe side effects as well. See e.g. the reference below:
Das S, Bhowmick S, Tiwari S, Sen S. An Updated Systematic Review of the
Therapeutic Role of Hydroxychloroquine in Coronavirus Disease-19 (COVID-19).
Clin Drug Investig. 2020 Jul;40(7):591-601. doi: 10.1007/s40261-020-00927-1.
PMID: 32468425; PMCID: PMC7255448. 

<img src="/home/chris.vanoevelen/workflows/tlsc-dsfb26v-20_workflows/images/lancet_covid.png" width="948" />
<p style="font-size:14px">https://www.thelancet.com/journals/lancet/article/PIIS0140-6736(20)31180-6/fulltext</p>

<div class="question">
##### Exercise 1 {-}

**Answer the following questions**

(A) What was the reason for retracting this [paper](https://www.thelancet.com/journals/lancet/article/PIIS0140-6736(20)31180-6/fulltext)?



(B) Why is the retraction in itself a problem?



(C)  In the sense that we defined above, does The Lancet adhere to Reproducible (Open) Science? Why does it / Why not, what is missing?

</div>

<details><summary>Click for the answer</summary>
Would the Lancet have adopted the Reproducible (Open) Science framework:

 >- There would have been no publication, so no retraction necessary
 >- The manuscript of this paper would not even have made it through the first check round
 >- All data, code, methods and conclusions would have been submitted
 >- This would have enabled a complete and thorough peer-review process that includes replication of (part of) the data analysis of the study
 >- Focus should be on the data and methods, not on the academic narratives and results ...
 >- In physics and bioinformatics this is already common practice

</details>

## Data, methods and logic

So in order to perform Reproducible Open Science we need to make a full connection between the data, the analysis and the narratives (the conclusions, the 'story', etc.). In *[Brown, Kaiser & Allison, PNAS, 2018](https://doi.org/10.1073/pnas.1708279115)*
We read:

"...in science, three things matter:

 >1. the data, 
 >1. the methods used to collect the data [...], and 
 >1. the logic connecting the data and methods to conclusions,

everything else is a distraction."

So what happens if we do not adhere to this principle?

 - The connection between the theoretical knowledge and the supporting data could get lost
 - The integrity of the data can become compromised (the data can get corrupt)
 - The steps from the (raw) data to the final conclusions are not well documented and cannot be traced or reproduced
 - The tools that were used to generate the analysis results are unavailable to others (this problem arises when licensed software is used in stead of open source tools)
 - The underlying mechanisms of algorithms used is unclear and not transparent  
 - The data is not available for control or reuse
 - The underlying assumptions for the data cannot be verified
 ...

I will illustrate this with the use of Excel in genome biology

### Why using Excel for Biology is a bad idea

Start with reading the following news article in The Guardian: [click](https://www.theguardian.com/politics/2020/oct/05/how-excel-may-have-caused-loss-of-16000-covid-tests-in-england)

That was a proper mess...

When you use Excel for data collection and especially for genetics and genomics studies, you risk losing and/or messing up your data. This is mainly due to the 'autoformatting' in Excel, but other problems could occur as well. This is nicely adressed in this [paper:](https://genomebiology.biomedcentral.com/articles/10.1186/s13059-016-1044-7). The authors show, through an automated workflow, that many Excel files used for genomics studies, and that were supplied as supplementary materials to a publication contain, 'auto formatted' (read _changed_) gene names. 

In itself this 'auto formatting' behaviour is problematic enough, but when you have data containing time series or dates, things start to become really problematic when you use Excel.

Also, if only one record in a whole Excel file is changed to the wrong data-type, R and other tools will parse this column most likely as a character. This stresses the need for thoroughly checking your data types, especially after importing Excel files into R.

We will practice this a bit and see this happening live in an exercise 

<div class="question">
##### Exercise 1 {-}

**Reading a strangely formatted column from an Excel file**

 A) From within R, try downloading the following file: 
 http://genesdev.cshlp.org/content/suppl/2009/06/11/gad.1806309.DC1/FancySuppTable2.xls
 B) What problems do you encounter, when trying to import this Excel file using `{readxl}`?
 C) Perform a manual download of this file by going [here:](http://genesdev.cshlp.org/content/suppl/2009/06/11/gad.1806309.DC1). You need the file under the link `Supp Table 2.xls`
 D) Why is manually downloading this file a problem with regard to open science?
 E) Import the manually downloaded Excel file into R
 F) Download [this file](https://ndownloader.figstatic.com/files/7148432)
 F) Open the file and compare the contents of the file to the Supplementary table shown [here](https://genomebiology.biomedcentral.com/articles/10.1186/s13059-016-1044-7#Sec1). Look specifically at the column `Example Gene Name Conversion`. What do you observe? Why do you think this is happening?
 G) Look at this article in the Microsoft help: https://support.microsoft.com/en-us/office/stop-automatically-changing-numbers-to-dates-452bd2db-cc96-47d1-81e4-72cec11c4ed8
 H) Change the column `Example Gene Name Conversion` in the file 
[here:](http://genesdev.cshlp.org/content/suppl/2009/06/11/gad.1806309.DC1) to text. 
 I) Change the column named `GENE SYMBOL` in [this file](http://genesdev.cshlp.org/content/suppl/2009/11/03/23.21.2484.DC2/Bilodeau_Supp_Table_11.xls) to text.
 J) Now try to find the wrongly converted gene called `40059` in this data file
 H) On the basis of your observations in this exercise: what are your conclusions about using Excel. How could you make the use of Excel _safer_ for data collection and analysis? What would you recommend your peers? Write (in Rmd) a short recommendation on the safe use of Excel for data collection (min 200 words).



</div>

<div class="rstudio-tip">
**TIPS** 
I always have difficulty remembering how to rotate axis labels in R. That is why I wrote an R package that has a convenient function. The package can be installed by running:
```
# install.packages("devtools") ## if not already installed
devtools::install_github("uashogeschoolutrecht/toolboxr")
## load the package
library(toolboxr)
```
The function you need from `{toolboxr}` is `rotate_axis_labels()`. Type
`?rotate_axis_labels()` in the R Console to see how to use this function. 

If you have any suggestions for a good convenience function to add to this package, create an issue on github.com for a feature request or clone/fork the repository, add the function you would like to add and create a pull request. You will learn how to take these steps in lesson 2 and 3.
</div>


## Portfolio assignment 1.1  {-}
<div class="dagopdracht">

**_C. elegans_ plate experiment** 

(Again: work out this exercise in a Rmarkdown file in your portfolio-project. You will need this later to put in your portfolio)

The data for this exercise was kindly supplied by J. Louter (INT/ILC) and was derived from an experiment in which adult _C.elegans_ nematodes were exposed to varying concentrations of different compounds. The variables `RawData` (the outcome - number of offspring counted as an integer value, after incubation time), `compName` (the generic name of the compound/chemical), the `compConcentration` (the concentration of the compound), and the `expType` are the most important variables in this dataset.

A typical analysis with this data would be to run a dose-response analysis using a log-logistic model with estimates for the maximal, the minimal, the IC50 concentration and the slope at IC50. We will not go into the details but a good package to run such computations and create graphs in R is the `{drc}` package. [See:](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0146021) [and:](https://cran.r-project.org/web/packages/drc/index.html). In the exercise below we will create some visualizations using `{ggplot2}`.

(A) Review the following Excel file in the `./data/CE.LIQ.FLOW.062_Tidydata.xlsx` <a href="https://github.com/DataScienceILC/tlsc-dsfb26v-20_workflows/raw/main/data/CE.LIQ.FLOW.062_Tidydata.xlsx" download> (it's here)</a>, by opening the file in Excel. See if you can spot anything peculiar about this file. Do not edit the file in any way. Just close it when you are done. (Annoyingly, Excel asks you to save your changes, even if you did not touch anything in the file: why is this cumbersome?)
 
(B) Open the file in R, using the `{readxl}` package.
 


(C) Inspect the data types of columns `RawData`, `compName` and `compConcentration`. What types would you expect from the experimental description above. Have the data types been correctly assigned during the importing of the data into R?



(D) Create a graph displaying a scatterplot for the `CE.LIQ.FLOW.062_Tidydata.xlsx` data, for the different compounds and the varying concentrations. Put the `compConcentration` on the x-axis, the `DataRaw` counts on the y-axis and assign a colour to each level in `compName`. Assign a different symbol (`shape = `) to each level in the `expType` variable. Try fixing the labels of the x-axis so that we can read them.



(E) When creating the plot under C), what happened with the ordering of the x-axis labels. Explain why this happens. Look at the data-type of the `compConcentration` column in the data again to find a clue.

(F) Correct the data-type of `compConcentration` to `numeric` and than look at the graph again. Use a log10 transformation on the x-axis to get a clear graph. Also, add a bit of `jitter` to the points in the graph so that points are not overlapping.  


Fill in:
(G) The positive control for this experiments is .....
(H) The negative control for this experiment is .....

(I) Think about how you would analyze this experiment to learn whether there is indeed an effect of different concentrations on offspring count and whether the different compounds have a different curve (IC50). Write down you analysis as a step-wise plan 
(J) Normalize the data for the `controlNegative` in such a way that the mean value for `controlNegative` is exactly equal to 1 and that all other values are expressed as a fraction thereof. Rerun your graphs with the normalized data. 
(H) Why would you want to take the step under J?

</div>

## When things go terribly wrong

In *[Brown, Kaiser & Allison, PNAS, 2018](https://doi.org/10.1073/pnas.1708279115)* we also read:

 "In one case, a group accidentally used reverse-coded variables, making their conclusions the opposite of what the data supported."

 "In another case, authors received an incomplete dataset because entire categories of data were missed; when corrected, the qualitative conclusions did not change, but the quantitative conclusions changed by a factor of >7"

These are common mistakes and if no checks or tests are build in than the conclusions from a study could be completely wrong. This does not only lead to bad science, it can be dangerous.

How would you mitigate such a risk?
We can start by doing everything we do in code via scripting. The preferred way to do this is, is by using literate programming such as is done when using RMarkdown. In this course we call this `RMarkdown driven development`

## Programming is essential for Reproducible (Open) Science
Because we can only connect the data, the methods used to collect the data and the narratives, so how the results were obtained, by using code. And we can create a script and multiple types of output from a single script by using RMarkdown, it is the perfect tool for enabling Open Resproducible research.

 >- Only programming an analysis (or creation of a graph) records every step
 >- The script(s) function as a (data) analysis journal 
 >- Code is the logic that connects the data and methods to conclusions 
 >- Learning to use a programming language takes time but pays of at the long run (for all of science)
 >- Using literate programming (RMarkdown), enables to connect everything together in a single script

**(Literate) programming is a way to connect narratives to data, methods and results**


```{.r .Rchunk}
knitr::include_graphics(file.path(image_dir,"rmd_printscr.png"))
```

<img src="/home/chris.vanoevelen/workflows/tlsc-dsfb26v-20_workflows/images/rmd_printscr.png" width="539" />

## A short example of Reproducible (Open) Science
The statistical model used in the example below is a so called mixed effects model. It is specifically good in modelling repeated measures, for example over time, or within a certain group or loacation, or as in this case from the same person. The R package that can be used to model this somewhat more complicated designs is the `{nlme}` package. The exact details for the model illustrated here are not so important. The example serves to show you how you would document a full analysis from begin to end, adhering to the Reproducible Research principles discussed in this chapter. If you would like to learn more about this type of analysis, [this is good starting point:](http://milton-the-cat.rocks/home/adventr.html#Contents_of_adventr) 

Assume we have the following question:

"Which of 4 types of chairs takes the least effort to arise from when seated in?"

We have the following setup:

 - 4 different types of chairs
 - 9 different subjects (probably somewhat aged)
 - Each subject is required to provide a score (from 6 to 20, 6 being very lightly strenuous, 20 being extremely strenuous) when arising from each of the 4 chairs. There is some 'wash-out' time in between the trials. The chair order is randomised.

To analyze this experiment statistically, the model would need to include: the rating score as the **measured (or dependent) variable**, the type of chair as the **experimental factor** and the subject as the **blocking factor**

### Mixed effects models

A typical analysis method for this type of repeated measures design is a so-called 'multi-level' or also called 'mixed-effects' or 'hierarchical' models. An analysis method much used in clinical or biological scientific practice. You could also use one-way ANOVA but I will illustrate why this is not a good idea 

### What do we minimally need, to replicate the science of this experiment? 

I will show:

 >- the data 
 >- an exploratory graph 
 >- a statistical model 
 >- the statistical model results
 >- a model diagnostic (logic why this is suitable model)
 >- some conclusions 
 
When performing statistics, it is important to realize that no single model is the correct or best model. There are always multiple options and trade-offs to be made. The most important learning lesson here is: 

**"In the end it matters more that insight is provided into what assumptions were made for the experiment/the data/the subject and the model, and not so much as which model is best."**. The way to do this is, is _again_ with writing a script that records all the steps and choices made. And of course, generating graphs also helps ;-)
 
In the next paragraph, I will try to show you the power of (literate) programming to communicate such an analysis. 

<p style="font-size:14px">[Example reproduced from: Pinheiro and Bates, 2000, _Mixed-Effects Models in S and S-PLUS_, Springer, New York.](https://cran.r-project.org/web/packages/nlme/index.html)</p>
 
### The data of the experiment

<p style="font-size:14px">[Wretenberg, Arborelius & Lindberg, 1993](https://doi.org/10.1080/00140139308967910)</p>
The data is available as a `data.frame` in the `{nlme}` package, which is a much valued R package for running multi-level statistical models. Below we import the data as a `tibble` (glorified `data.frame`) 


```{.r .Rchunk}
library(nlme)
ergoStool %>% as_tibble()
```

```{.Rout}
## # A tibble: 36 × 3
##    effort Type  Subject
##     <dbl> <fct> <ord>  
##  1     12 T1    1      
##  2     15 T2    1      
##  3     12 T3    1      
##  4     10 T4    1      
##  5     10 T1    2      
##  6     14 T2    2      
##  7     13 T3    2      
##  8     12 T4    2      
##  9      7 T1    3      
## 10     14 T2    3      
## # … with 26 more rows
```
<p style="font-size:18px">The `lme()` function is part of the [`{nlme}`](https://cran.r-project.org/web/packages/nlme/index.html) package for mixed effects modelling in R</p>

### An exploratory graph
First step is (always) plot all the data that you have. Or, in case you have very much data, take a random sample and plot that. A scatter plot is a very good start. It provides you already with an idea on the spread of some variables (here we plot the dependent on the y-axis and some predictor variable on the x-axis). The seed is for reproducibility. Which function in the code below is dependent on a random number generator?

```{.r .Rchunk}
set.seed(123)
plot_ergo <- ergoStool %>%
  ggplot(aes(x = reorder(Type, effort), y = effort)) + 
  geom_boxplot(colour = "darkgreen", outlier.shape = NA) + 
  geom_jitter(aes(colour = reorder(Subject, -effort)), 
              width = 0.2, size = 3) +
  scale_colour_manual(
    values = c(
      "red","blue", 
      "green", "darkblue", 
      "darkgreen", "purple", 
      "grey", "black", "darkgrey")
    ) +
  ylab("Effort (Borg scale score)") +
  xlab("Chair type") + 
  guides(colour=guide_legend(title="Subject id")) +
  theme_bw()
plot_ergo
```

<img src="lesson-01-reproducible-research_files/figure-html/unnamed-chunk-11-1.png" width="672" />

<div class="question">
##### Exercise 1 {-}

**Mind the variability per subject, what do you see?**

 (A) Can you say something about within-subject variability (note 'Minster Blue')?
 (B) Can you say something about between-subject variability (note 'Mister Green', vs 'Mister Black')?
 (C) Which chair type takes, on average the biggest effort to arise from?
 (D) Looking at the code, why do you think the x-axis is not displaying the `Chair type` in a numeric order?
 
</div>

### The statistical questions
When we look at the scientific question and the data, we can deduce a number of statistical questions

 1. Which chair type takes, on average the biggest effort to arise from?
 2. What model would best capture the variability we see in the data, how would we reflect for example the inter-personal variability we observed in the exercise above, in a model
 3. Do individual (within subject) differences play a role in appointing a average score to a chair type? (MEM, random effects)
 4. Does variability between subjects play a role in determining the 'best' chair type (ANOVA / MEM, confidence intervals)
 5. What numbers can we appoint to the questions above? Numbers in statistics are usually called parameters.

### The statistical model 
Statistical models (in R) can be specified by a `model formula`. The left side of the formula is the dependent variable, the right side are the 'predictors'. Here we include a `fixed` and a `random` term to the model (as is common for mixed-effects models). The fixed and random terms in the model are terms that reflect here the randomization (over persons) and the inter-person variability we observe in the data.


```{.r .Rchunk}
ergo_model <- lme(
  data = ergoStool, # the data to be used for the model
  fixed = effort ~ Type, # the dependent and fixed effects variables
  random = ~1 | Subject # random intercepts for Subject variable
)
```

We choose here to allow each volunteer to have its own curve, that has an intercept with the y axis. For sake of simplicity we assume the curves run parallel, so we assume a fixed slope. In more complicated designs we could also include a random slope, that allows the curves to vary in slope. This can be interpreted as that the effect of `Chair type` on `Effort` is not equal for each combination of Chair type and subject. 

Lets see if the assumption of fixed slope holds:

```{.r .Rchunk}
plot_ergo_slopes <- ergoStool %>%
  ggplot(aes(x = reorder(Type, effort), y = effort)) + 
  geom_jitter(aes(colour = reorder(Subject, -effort)), 
              width = 0.2, size = 3) +
  geom_smooth(aes(group = Subject, colour = Subject), method = "lm", se = FALSE) +
  scale_colour_manual(
    values = c(
      "red","blue", 
      "green", "darkblue", 
      "darkgreen", "purple", 
      "grey", "black", "darkgrey")
    ) + 
  ylab("Effort (Borg scale score)") +
  xlab("Chair type") + 
  guides(colour=guide_legend(title="Subject id")) +
  theme_bw()
plot_ergo_slopes
```

<img src="lesson-01-reproducible-research_files/figure-html/unnamed-chunk-13-1.png" width="672" />

What do you think? Is the assumption for a fixed slope defensible?

### The statistical results

```{.r .Rchunk}
result <- ergo_model %>% summary() 
result$tTable %>% as.data.frame() %>% knitr::kable()
```



|            |     Value| Std.Error| DF|   t-value|   p-value|
|:-----------|---------:|---------:|--:|---------:|---------:|
|(Intercept) | 8.5555556| 0.5760123| 24| 14.853079| 0.0000000|
|TypeT2      | 3.8888889| 0.5186838| 24|  7.497610| 0.0000001|
|TypeT3      | 2.2222222| 0.5186838| 24|  4.284348| 0.0002563|
|TypeT4      | 0.6666667| 0.5186838| 24|  1.285305| 0.2109512|

### Model diagnostics

 >- Diagnostics of a fitted model is the most important step in a statistical analysis
 >- In most scientific papers these details are lacking 
 >- If no model diagnostics are present, the question arises: Did the authors omit to perform this step? Or did they just not report it?
 >- If you do not want to include it in your paper, put it in an appendix, or even better, online together with the dat and the analysis script(s)!
 
A residual plot shows the 'residual' error ('unexplained variance') after fitting the model. Under the Normality assumption standardized residuals should:
 
 >1. Be normally distributed around 0
 >1. Display no obvious 'patters'
 >1. Should display overall equal 'spread' above and below 0 ('assumption of equal variance')

The details of the residual plot and the underlying theory do not matter much here. You only have to look at the plot and assess whether tha above assumptions are met or not.
 
### Residual plot

```{.r .Rchunk}
plot(ergo_model) ## type = 'pearson' (standardized residuals)
```

<img src="lesson-01-reproducible-research_files/figure-html/unnamed-chunk-15-1.png" width="672" />

### The conclusions in a plot
We will spend a Masterclass on creating 'publication grade' graphs. Here is one that you could find in a paper about the `ergoStool` experiment and the analysis we did above.

```{.r .Rchunk}
# install.packages("ggsignif")
library(ggsignif)
p_values <- result$tTable %>% as.data.frame()
annotation_df <- data.frame(Type=c("T1", "T2"), 
                            start=c("T1", "T1"), 
                            end=c("T2", "T3"),
                            y=c(16, 14),
                            label=
                              paste("p-value:",
                              c(
                              formatC(
                                p_values$`p-value`[2], digits = 3),
                              formatC(
                                p_values$`p-value`[3], digits = 3)
                              )
                            )
                          )
                            
set.seed(123)
ergoStool %>%
  ggplot(aes(x = reorder(Type, effort), 
             y = effort)) + 
  geom_boxplot(colour = "darkgreen", 
               outlier.shape = NA) + 
  geom_jitter(aes(
    colour = reorder(Subject, -effort)), 
    width = 0.2, 
    size = 3) +
  scale_colour_manual(
    values = c(
      "red", "blue","green", 
      "darkblue", "darkgreen", 
      "purple", "grey", "black", 
      "darkgrey")) +
  ylab("Effort (Borg scale score)") +
  xlab("Chair type") + 
  guides(colour=guide_legend(title="Subject id")) +
  ylim(c(6,20)) +
  geom_signif(
    data=annotation_df,
    aes(xmin=start, 
    xmax=end, 
    annotations=label, 
    y_position=y),
    textsize = 5, vjust = -0.2,
    manual=TRUE) +
  theme_bw() -> plot_ergo
plot_ergo
```

<img src="lesson-01-reproducible-research_files/figure-html/unnamed-chunk-16-1.png" width="672" />


## Example; The Open Science Framework [OSF](https://osf.io/)
To enable and facilitate the practice op Open Science, there are a number of organizations and foundations that support researchers. Below are a few examples. It is helpful to know about them if you are looking for places to get data, share data and code and to find good practices and examples.

```{.r .Rchunk}
knitr::include_graphics(
  here::here(
    "images",
    "cos-shield.png")
)
```

<img src="/home/chris.vanoevelen/workflows/tlsc-dsfb26v-20_workflows/images/cos-shield.png" width="125" />

$Reproducible\ Science = P + D + C + OAcc + OSrc$ 

**OSF has it all**

<p style="font-size:14px">$P = Publication$, $D = Data$, $C = Code$, $OAcc = Open\ Access$, $OSrc = Open\ Source$ </p> 

### OSF - Reproducible Project: Psychology

 >- 100 publications in Psychology journals
 >- Results from half of these publications could be reproduced
 >- Full access to P, D and C in [OSF](https://osf.io/ezcuj/)
 >- The publication is not published in an OAcc journal but:
 >- [The submitted manuscript is available in OSF](http://pps.sagepub.com/content/7/6/657.abstract)
 >- [The R code used is available in OSF](https://osf.io/fkmwg/)  
 
### Another journal that supports Open Science is F1000 Research
The journal can be found [here](https://f1000research.com/).
Have a look at the special Bioconductor channel: https://f1000research.com/gateways/bioconductor


## Portfolio assignment 1.2 {-}
<div class="dagopdracht">

**Open Peer Review**

This exercise is about identifying reproducibility issues in a scientific publication. We use the criteria for reproduciblity that are publically available [via here](https://www.researchgate.net/publication/340244621_Reproducibility_and_reporting_practices_in_COVID-19_preprint_manuscripts)

| Transparency Criteria| Definition       | Response Type|
|---------|-------------------------------|----------|
|Study Purpose |A concise statement in the introduction of the article, often in the last paragraph, that establishes the reason the research was conducted. Also called the study objective.| Binary| 
|Data Availability Statement | A statement, in an individual section offset from the main body of text, that explains how or if one can access a study’s data. The title of the section may vary, but it must explicitly mention data; it is therefore distinct from a supplementary materials section.| Binary|
|Data Location | Where the article’s data can be accessed, either raw or processed.| Found Value|
|Study Location| Author has stated in the methods section where the study took place or the data’s country/region of origin.| Binary; Found Value|
|Author Review| The professionalism of the contact information that the author has provided in the manuscript.|Found Value|
|Ethics Statement | A statement within the manuscript indicating any ethical concerns, including the presence of sensitive data.|Binary|
|Funding Statement| A statement within the manuscript indicating whether or not the authors received funding for their research.|Binary|
Code Availability | Authors have shared access to the most updated code that they used in their study, including code used for analysis. |Binary|

**Table clarification** The `Transparency Criteria` are criteria you need to score the article of your choice for. Read them carefully and discuss with another course participant if you do not understand them. 
Each Tranparance criterion comes with a `Definition` that explains the criterion in more details. These descriptions are particularly helpful to understand what the criterium entails and what to look for in the article. The `Response Type` is the actual score  

In this assisgment you need to find a scientific article yourself, using PubMed or another database or repository. Use only **Open Access** articles. Having an article in hand, go over the table above and score the article according the criteria. **<mark>Be sure to select a primary article that presents a study using data from experimental work </mark>**. This can be laboratory experiments or _in silico_ experiments. Reviews and meta analysis are not suitable for this assignment     

To guide your search you can choose between these topics

 - "Coronavirus / COVID-19"
 - "The effects of compound on an organism / Toxicology"
 - "The effectiveness of a drug or treatment in an animal study"
 - "The effects of a compound investigated in a cell or organoid system"
 
**TIPS**

 - If you do not know where to start your literature search start here: https://www.biorxiv.org/
 - This assignment is not about the topic you select, so try to do that quickly
 - You may want to cheat and select an article that scores TRUE on the `Data Availability Statement`, because that enables you to use the this article again in one of the next assignments.

**PART 1**
_To complete part 1, execute activity A to G_ 
 
(A) Initiate an empty RMarkdown file in your RStudio environment and provide author and title (after the title of this exercise)
(B) Search for a primary Open Access article on one of the above listed topics, using Pubmed Central
(C) Read the article diagonally to check if is indeed a primary article describing emperical scientific findings. 
(D) Include the reference to this article in your Rmd file
(E) Score the article on the basis of the above 'Repita' criteria
(F) Write an Rmarkdown report on your findings, including the table above and some information about the article such as general aim, short methods and results. If data is available, try including some  
(G) Store the source Rmd and knitted HTML in a folder called 'Rmd' in your course RStudio project. You will need it again later in the course

**PART 2** 
_To complete this assignment you will have to execute activity H to P_

(H) Using the [OSF website](https://osf.io/), select a project that addresses an aspect of the SARS-Cov-2 virus. 
(I) Select a project that has a dataset and R-code shared in the project environment. 
(J) Have a look at the code. Describe in your own words what the code intents to achieve.
(K) In terms of readibility of the code, how would you grade (1(very bad)-5(very good)) the code available.
(L) Download the code and the data to a new RStudio project
(M) Run the script or code that is available to reproduce at least 1 figure
(N) When you encounter errors or flaws in the script, try fixing them and record your changes.
(O) Taken together on a scale from 1 (very hard) to 5 (very easy), how much effort did it take you to reproduce the visualization from the project, report or article
(P) Generate an RMarkdown script that contains the details on the project you selected, the code you used to create the visualization and your score for reproducibility.

resource: https://www.researchgate.net/publication/340244621_Reproducibility_and_reporting_practices_in_COVID-19_preprint_manuscripts/fulltext/5e81f9fd92851caef4ae37ba/Reproducibility-and-reporting-practices-in-COVID-19-preprint-manuscripts.pdf

</div> 
 
## Resources

https://www.displayr.com/what-is-reproducible-research/

https://book.fosteropenscience.eu/en/02OpenScienceBasics/04ReproducibleResearchAndDataAnalysis.html