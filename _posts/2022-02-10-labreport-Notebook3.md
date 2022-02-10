---
title: Lab Notebook 3
tags: Notebook
---

# Lab Notebook 3
## RegEx Expressions and Commentary
In this section I will detail the variety of approaches I took to cleaning the initial data. Specifically, I will work through two specific attempts. The first attempt is a longer and more tedious use of the RegEx system. In the second approach, with the assistance of Professor Thomas, we were able to devise a regular expression that was able to effectively remove special characters with one input. Hopefully, the work that I present here will be useful for my colleagues and anyone interested in engaging with RegEx. 

### First Attempt

Below, I have provided my step-by-step deployment of the regular expressions commands. You will notice that the first seven steps are my attempts to eliminate special characters. This was completed prior to Professor Thomas' office hours where we devised a regular expression that would effectively capture all special characters. As you will no doubt notice, this attempt is marked by a certain tedium. During this attempt, I worked to familiarize myself with the system and the *literality of regular expressions*. One wrong move, and it's as if the entire system falls apart... Don't we all love computers?

In this attempt I have **not** provided the results of each input. In my second attempt, I will provide the regular expressions and substitutions used, and the output that I received. 

1. RegEx: ,
2. RegEx: ;
3. Sub: ,
4. RegEx: &amp,
5. Sub: &
6. RegEx: [()]
7. RegEx: [[] ]
8. RegEx: ]
9. RegEx: "
10. RegEx: New York ed.
11. RegEx: amp
12. RegEx: Denver Colo.
13. Sub: Denver CO
14. RegEx: MA
15. RegEx: Boston
16. Sub: Boston MA
17. RegEx: Washington D.C.
18. Sub: Washington DC
19. RegEx: Hayward WI.[?]
20. Sub: Hayward WI
21. RegEx: Baltimore Md.
22. Sub: Baltimore MD
23. RegEx: Fairfax Virginia
24. Sub: Fairfax VA
25. RegEx: Paramus N.J
26. Sub: Paramus NJ

### Second Attempt

**Raw Test String**
```
The Epoch Times, New York ed.; New York (NY)
"La Voz Bilingüe"; Denver, Colo.
Jewish Advocate; Boston
Washington Informer; Washington, [D.C.]
News from Indian Country; Hayward, WI.?
Afro - American, 5 Star edition; Baltimore, Md.
Diverse Issues in Higher Education; Fairfax Virginia
The Gay &amp; Lesbian Review Worldwide; Boston, MA
"The Hispanic Outlook in Higher Education; [Paramus N.J
```

1.[_%+,"?()\[\]]+

``````
The Epoch Times New York ed.; New York NY
La Voz Bilingüe; Denver Colo.
Jewish Advocate; Boston
Washington Informer; Washington D.C.
News from Indian Country; Hayward WI.
Afro - American 5 Star edition; Baltimore Md.
Diverse Issues in Higher Education; Fairfax Virginia
The Gay &amp; Lesbian Review Worldwide; Boston MA
The Hispanic Outlook in Higher Education; Paramus N.J
``````

2.RegEx: &amp;

2a. Sub: &
	
``````
The Epoch Times New York ed.; New York NY
La Voz Bilingüe; Denver Colo.
Jewish Advocate; Boston
Washington Informer; Washington D.C.
News from Indian Country; Hayward WI.
Afro - American 5 Star edition; Baltimore Md.
Diverse Issues in Higher Education; Fairfax Virginia
The Gay &amp; Lesbian Review Worldwide; Boston MA
The Hispanic Outlook in Higher Education; Paramus N.J
``````
	
3.RegEx: ;

3a. Sub: ,

``````
The Epoch Times New York ed., New York NY
La Voz Bilingüe, Denver Colo.
Jewish Advocate, Boston
Washington Informer, Washington D.C.
News from Indian Country, Hayward WI.
Afro - American 5 Star edition, Baltimore Md.
Diverse Issues in Higher Education, Fairfax Virginia
The Gay & Lesbian Review Worldwide, Boston MA
The Hispanic Outlook in Higher Education, Paramus N.J
``````

4.RegEx: Colo.

4a. Sub: Denver CO

``````
The Epoch Times New York ed., New York NY
La Voz Bilingüe, Denver CO
Jewish Advocate, Boston
Washington Informer, Washington D.C.
News from Indian Country, Hayward WI.
Afro - American 5 Star edition, Baltimore Md.
Diverse Issues in Higher Education, Fairfax Virginia
The Gay & Lesbian Review Worldwide, Boston MA
The Hispanic Outlook in Higher Education, Paramus N.J
``````
	
5.RegEx: MA

``````
The Epoch Times New York ed., New York NY
La Voz Bilingüe, Denver CO
Jewish Advocate, Boston
Washington Informer, Washington D.C.
News from Indian Country, Hayward WI.
Afro - American 5 Star edition, Baltimore Md.
Diverse Issues in Higher Education, Fairfax Virginia
The Gay & Lesbian Review Worldwide, Boston 
The Hispanic Outlook in Higher Education, Paramus N.J
``````

6.RegEx: Boston

6a. Sub: Boston MA

``````
The Epoch Times New York ed., New York NY
La Voz Bilingüe, Denver CO
Jewish Advocate, Boston MA
Washington Informer, Washington D.C.
News from Indian Country, Hayward WI.
Afro - American 5 Star edition, Baltimore Md.
Diverse Issues in Higher Education, Fairfax Virginia
The Gay & Lesbian Review Worldwide, Boston MA 
The Hispanic Outlook in Higher Education, Paramus N.J
``````
	
7.RegEx: D.C.

7a. Sub: DC

``````
The Epoch Times New York ed., New York NY
La Voz Bilingüe, Denver CO
Jewish Advocate, Boston MA
Washington Informer, Washington D.C.
News from Indian Country, Hayward WI.
Afro - American 5 Star edition, Baltimore Md.
Diverse Issues in Higher Education, Fairfax Virginia
The Gay & Lesbian Review Worldwide, Boston MA 
The Hispanic Outlook in Higher Education, Paramus N.J
``````

8.RegEx: WI.

8a. Sub: WI

``````
The Epoch Times New York ed., New York NY
La Voz Bilingüe, Denver CO
Jewish Advocate, Boston MA
Washington Informer, Washington DC
News from Indian Country, Hayward WI
Afro - American 5 Star edition, Baltimore Md.
Diverse Issues in Higher Education, Fairfax Virginia
The Gay & Lesbian Review Worldwide, Boston MA 
The Hispanic Outlook in Higher Education, Paramus N.J
``````
	
9.RegEx: Md.

9a. Sub: MD

``````
The Epoch Times New York ed., New York NY
La Voz Bilingüe, Denver CO
Jewish Advocate, Boston MA
Washington Informer, Washington DC
News from Indian Country, Hayward WI
Afro - American 5 Star edition, Baltimore MD
Diverse Issues in Higher Education, Fairfax Virginia
The Gay & Lesbian Review Worldwide, Boston MA 
The Hispanic Outlook in Higher Education, Paramus N.J
``````
	
10.RegEx: Virginia

10a. Sub: VA

``````
The Epoch Times New York ed., New York NY
La Voz Bilingüe, Denver CO
Jewish Advocate, Boston MA
Washington Informer, Washington DC
News from Indian Country, Hayward WI
Afro - American 5 Star edition, Baltimore MD
Diverse Issues in Higher Education, Fairfax VA
The Gay & Lesbian Review Worldwide, Boston MA 
The Hispanic Outlook in Higher Education, Paramus N.J
``````
	
11.RegEx: N.J

11a. Sub: NJ

``````
The Epoch Times New York ed., New York NY
La Voz Bilingüe, Denver CO
Jewish Advocate, Boston MA
Washington Informer, Washington DC
News from Indian Country, Hayward WI
Afro - American 5 Star edition, Baltimore MD
Diverse Issues in Higher Education, Fairfax VA
The Gay & Lesbian Review Worldwide, Boston MA 
The Hispanic Outlook in Higher Education, Paramus NJ
``````

In the second attempt I have provided the raw initial test string, the regular expression and substitution inputs used, and the output received. Hopefully this will allow my interested colleagues to reproduce the steps I deployed. 

You may also notice an interesting discrepancy between the first and second attempt. If one follows the outputs provided in the first attempt, one **will not** receive the output of the second attempt. This is because of certain framing biases that I deployed in my initial "cleaning" of the data. For one, Step 8 of the first attempt asks users to remove "New York ed.". I removed this because I did not feel as if it was relevant information. I have corrected this and left in "New York ed." in my second attempt. Second, Professor Thomas' completed .csv file keeps in "&amp". I have decided to remove "&amp" and replace it with the simple ampersand symbol for my own clarity. As Professor Thomas explained, the "amp" is the unicode expression for the ampersand command but I have decided that this "amp" is superfluous information for presupposed readers of the dataset. My completed test string can be found beneath Step 11 above. 

## Reflections
My work with regular expressions this week made me encounter a particular paradox with my own relationship to "data". Our activity this week effectively modeled the concept of "cleaning"; that is, using regular expressions to make data legible to a computer scripting program or software. "Cleaning" this data is time-consuming but monumentally useful. When I encountered the data Professor Thomas provided in its raw form, I immediately thought that it was ***messy***. 

Arguably, the very concept of messiness and its presupposition of an ordered placement is the defining object of critique for this week's readings. As Katie Rawson and Trevor Muñoz argue in "Against Cleaning," 
>The cleaning paradigm assumes an underlying, 'correct' order. However tidy values may look when grouped into rows or columns or neatly delimited records, this tidiness privileges the structure of a container, rather than the data inside it.

The concept of "messy" data seems, considered through the lens of Humanities work, antithetical to the notions of diversity, embodiment, marginality, and anti-hierarchical organizational networks upheld within large pockets of the discipline. Yet, one cannot deny looking at our raw test string from this week's lab, its messiness bespeaks a non-functionality. Considered through the structures of .csv and .tsv organizational requirements, this data *is messy*. It appears to me, then, that the "data cleaning" process that consumes "80% of data analysis"[^1] is actually *two processes*. 

The articles that we engaged with imply, or directly assert, this kind of bifurcated structure within the data cleaning process. There is, in a first move, an engagement with the raw data. It is, at this point, *not messy*. As a researcher works through the dataset and begins to find datapoint(s) that, in their current form, are not relevant to their research question, the researcher should note those points and continue. The researchers goal is to organize and narrow the scope of their engagement with a dataset and, as they make organizational moves or frame the data in particular ways, index their moves and structures. Once these parameters have been adequately defined, the researcher then works on cleaning the data within the circumscribed structure. These processes do not have to be linear either: the cleaning process may divulge new indexable information that can point towards future projects working with the same set of materials.

Further, these strategic framing and organization moves employed by researchers can be the subject of appendices exploring the rationale for the structuration of a dataset. For example, in the previous section I divulged that I presented the "&amp" as "&" in my finalized test string and provided my rationale: clarity for user engagement. Although this example is quaint and mundane, it also models practices of data **transparency**. Catherine D'Ignazio and Lauren Klein are helpful on this point: 
>... there is a way to build space for transparency plus reflexivity[^2] in data science, rather than undertaking projects that purport to be objective (but, as we have discussed, never really are). Transparency and reflexivity allow the people involved in any particular project to be explicit about the methods behind their project, as well as their own identities.
>*Data Feminism*, Ch. 5

Transparency is an effective practice for fostering data centric co-liberation. In a way, our blogs are built for precisely this purpose: openness and transparency.[^3]

[^1]: [Data Feminism, Chapter 5](https://data-feminism.mitpress.mit.edu/pub/2wu7aft8/release/3)
[^2]: To expand on the concept of Reflexivity, I am including a quote from Chapter 5 of Data Feminism: "This means disclosing your project’s methods, your decisions, and—importantly for work that strives to address injustice—your own positionalities."
[^3]: Also, thanks to Claire and her Github repository for helping me figure out how to put these footnotes in!
