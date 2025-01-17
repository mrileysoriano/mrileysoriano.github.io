---
title: Lab Notebook 4
tags: Notebook
---

# Lab Notebook 4
## Questions 1-5
1. How does this change the word cloud, and what are these changes telling you? 
	1. Removing the auto-detected stopwords allows common prepositions and articles to populate the word cloud. This includes words such as "and", "the", and so on. These words are commonly used in the English language but are, generally, non-substantive. Put differently, these words do not give us relevant information related to the discussion of the humanities in news documents. 
2. Why is relative frequency sometimes a more useful or accurate measure of a term’s importance than raw frequency? 
	1. Relative frequency can be useful in helping isolate substantial terms that appear in rapid succession within documents. In Voyant's case, it determines the relative frequency of words through a specific terms repetition per one million words. Looking at the WE1S Humanities dataset, we can determine that the term with the highest relative frequency is "mcas". We will explore the specifics of this word in the following question. As to the difference between relative and raw frequency: raw frequency tells us the number of times that a word is repeated throughout all of the documents fed into Voyant, whereas relative frequency isolates the terms that are used most often in relatively tight successions (per million). 
3. What is this document? And, more importantly, what have you learned about the term “mcas” in our corpus overall, and/or the utility or value of “significance” metrics like TF-IDF? 
	1. "MCAS" appears in document 442. Document 442 is a grievance letter directed to the board of the Morrissey College of Arts and Sciences over the termination of the school's honors program. The document contains signees at the bottom of the letter. Each signees space appears to begin with the student or faculty members name followed by the acronym for the school (MCAS) and concluding, possibly, with their year of graduation. "MCAS" is, within the scope of the overall corpus, non-essential information as it appears only once in the entirety of the dataset. Due to its rapid repetition within this one document, the TF-IDF significance score for "mcas" is artificially heightened in the corpus overall. TF-IDF scores should be carefully scrutinized to determine the legitimacy of the score and the context in which the term appears. There is a legitimate value in being able to determine the relative frequency of appearance of particular words, but cases such as "mcas" require careful attention to the context of a term's appearance. 
4. Looking through this list of terms and their “Comparison” values, what observations can you make about terms that are more likely to occur in the humanities corpus vs. terms that are more likely to occur in the science corpus? How are these terms different? 
	1. For the purposes of comparison, I will select the five most positively skewed terms and the five most negatively skewed terms. Positively skewed terms tend to appear in statistically significant frequency within the humanities corpus. Negatively skewed terms tend to appear in statistically significant frequency within the sciences corpus.
 
	- Humanities
		 - students (0.00630)
		 - humanities (0.00545)
		 - faculty (0.00241)
		 - studies (0.00238)
		 - courses (0.00220)
	
	- Science
		 - science (-0.00254)
		 - research (-0.00224)
		 - researchers (-0.00147)
		 - scientists (-0.00145)
		 - health (-0.00120)
	
	Based on the data above, we see that certain terms such as "students", "faculty", "studies", and "course" mediate discussions of the humanities and humanities research through the language of pedagogy and teaching. In fact, it is striking to note that in the humanities corpus "student" appears to be the most statistically significant term (based on relative frequency), whereas "science" is the most frequently used statistically significant term within the science corpus. Put another way, science research and researchers are highlighted for their contributions *as such*, whereas humanities newsletters are mediated through the language of teaching and pedagogy. 
5. What tool(s) did you explore? What did this tool(s) help you to observe about this data and/or what did you learn about this data using this tool(s)? Alternatively, what did you _hope_ to learn about this data using this tool and how (or why) did reality seem to fall short of that expectation? 
	1. After looking over the Voyant documentation I deployed the textual arc tool, which appears in the top left portion of the Voyant screen. The textual arc organizes the text in a linear, clockwise fashion and, as each term is repeated, the term is drawn closer to the center of the bubble. This tool seems useful for analyses of longer form novels or texts but its utility appears limited when analyzing the shorter form texts that comprise the Humanities and Science corpus. I expected the textual arc to provide a different gloss on the word cloud by highlighting position and statistical relevance within all documents but the tool is only useable with single texts thereby making large-scale batch analyses with this dataset difficult.
	
## Reflections
The Data-Sitters Club #6 is an exploration of the Baby-Sitters Club novels using Voyant. Specifically, Katherine Bowers goes into Voyant with a simple question: what can it tell us about the slang used in the BSC novels? Voyant is a powerful textual analysis tool. Part of this week's lab functioned as a tutorial to help us become acquainted with the basic components of the software. Bowers was able to use Voyant and its various visualization tools to compile a word cloud of unique slang terminology. The data visualization of slang words within the BSC novels was particularly helpful as it introduced the value of context into exploratory research. I am thinking, specifically, of Bower's investigation into the categorization and statistically significant frequency of the word "fresh" in BSC texts. Fresh, as it appears within Voyant's visualization tool, was not specific to a slang terminology. At times, it simply functioned in a descriptive manner. This term, then, did not fit into the categorization of slang terminology that Bowers was exploring. Fresh needed to be categorized as a stopword. That is, a word that has no significant weight within the boundaries of exploration.

Despite a minor learning curve, Voyant was actually intuitive and simple to use and provided a great deal of information. One of the questions above asked us to dig into the statistical significance and context of the term "mcas". Within the humanities dataset this term had a high relative frequency and therefore skewed statistical significance. Taken at face value, much like the word Fresh, it would appear that this term falls into the bounds of exploration. Yet, delving further into the terms context, it becomes evident that this term is not wholly relevant. It functions, within the wider body of the dataset, as an outlier. Now, one could conduct a focused analysis on identificatory markings, for example, within humanities documents but this appears to fall outside of the scope of a broader, large-scale data analysis. There is a nice homologous link, then, between the word "Fresh" in Bowers exploratory analysis and "mcas" in the WE1S humanities dataset. 

If I continue using DH methodological practices later in my career, I can already imagine Voyant, or something like it, being an essential tool. Being able to quickly and easily conduct at-a-glance analyses of large textual corpuses and terminology could prove invaluable for working with large databases. Out of all of the tools that we have used so far, Voyant seems to be the most readily accessible and visually intuitive. 
