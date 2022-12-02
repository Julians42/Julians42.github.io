---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

Education
======
* **Harvard University, 2023 (Expected)**
 * A.B. Candidate in Applied Mathematics, GPA: 3.94
 * Focus in Earth and Planetary Sciences. Secondary in Statistics
* **Middlebury Union High School, 2018**
 * Valedictorian, SAT: 1530 - M:800, V: 730, Vermont Scholar
* **Budapest Semesters in Mathematics**
 * *Combinatorial Optimization*, Grade: A, Spring 2021
* **Middlebury College**
 * M200: Linear Algebra, Audit, Spring 2017
 * M318: Operations Research, Grade: A, Fall 2017


Work experience
======
* **Harvard Undergraduate Forestry Data Science Group, Summer 2022**
 * Research Fellow through the URAF SPUDS Program
 * Investigated how to improve small area estimators with zero-inflated data for the US Forest Inventory and Analysis.
 * Worked with NCASI, an umbrella organization for foresters, to design improved visualization tools in the **R** programming language to better present uncertainty in climate change risk to tree species.


* **NOAA Hollings Scholar, Summer 2021**
 * Interned with the National Oceanic and Atmospheric Administration (NOAA) on a joint project at Boulder Physical Sciences Lab and at Princeton's Geophysical Fluid Dynamics Laboratory (GFDL) investigating snow droughts using large ensemble climate models. 
 * Research was conducted in **Python** via remote SSH connection. The Project was supervised by Mimi Hughes (PSL), Nathaniel Johnson (GFDL), and Kai-Chih Tseng (Princeton/GFDL, now Taiwan University).
 * The project is ongoing, and we are close to publication

* **Harvard Seismology / U. Washington Seismology Groups, Feb 2020 - May 2021**
 * Built a Julia workflow for high-performance seismic data analysis on the AWS cloud to constrain an LA-area earthquake and deployed workflow using 100 times more data than a 2014 study. 
 * Used AWS EC2, S3, and Batch for parallel computing alongside containerization, bash scripting, and GitHub to extend the workflow to begin building a California-wide database of seismology cross-correlations with 100+ TBs of data.
 * Several significant presentations, including AGU oral presentation, SCEC poster, video tutorials, and tutorial presented to the Stanford Seismology Group. 

Clubs and Extracurriculars
=====
* **Harvard Varsity Nordic Skiing, 2019-Present**
 * Walk-on member of the Harvard Nordic Ski team. Commit ~20 hours weekly to practice. 
 * Represented skiing on the Student-Athlete Advisory Committee 2020-22.

* **Applied Math Peer Concentration Advisor (PCA), 2021-22**
 * Coordinated the applied math advising team by facilitating 50 advisor/advisee pairings and 2-3 events per semester. 

* **Harvard Pops Orchestra, 2018-19 & 2022**
 * Played trumpet II for the Orchestra during my freshman year and junior spring.
 * In high school I played lead (first by audition) trumpet in the Vermont All-State Jazz Band and also played for the New England Concert Band

* **Harvard Data Analytics Group, Spring 2021**
 * Case Team Associate - responsible for coordinating feature and model development for 4 analysts. 
 * Led the development of a machine learning model to automate the grading of student writing samples for an ed-tech start-up. Merged team members' programs into one workflow and tested several machine learning algorithms. Improved modeled grading accuracy by 90% over the semester-long project.

* **Harvard Undergraduate Consulting for Business and the Environment, Spring 2019**
 * Developed a linear programming model to provide the client with the most cost-effective disposal solution for waste. Built a website to host the model and deploy other tools developed by case team members.


Skills
======
* Programming Languages: Python, R, Julia
 * Python: Data Analysis (NumPy, pandas, sklearn), Parallel Computing, Large Ensembles
 * R: Statistical Modeling, RShiny web development
 * Julia: Cloud Computing, Seismology Applications, and Packages
* Cloud Computing
 * AWS EC2 and S3 Platforms
 * AWS Batch Computing
 * Containerization (Docker)
 * Parallel Workflows


Selected Awards
======
* Detur Book Prize - *Fall 2019*
 * "The Detur Book Prize is one of the oldest prizes at Harvard College. It recognizes sophomores who attained very high academic standing in their first year at the College and honors them with a book of their choice." - Harvard College Office of Undergraduate Education
* NOAA Hollings Scholarship - *Spring 2020*
 * "The Hollings Scholarship Program provides successful undergraduate applicants with awards that include academic assistance (up to `$`9,500 per year) for two years of full-time study and a 10-week, full-time paid (`$`700/week) internship at an NOAA facility during the summer." - NOAA Hollings Program
* Mathworks Math Modeling Finalist - *Spring 2017 & 2018*
 * My Middlebury Mathematics Team competed in both the 2017 and 2018 national Moody’s, and subsequently MathWorks, Math Modeling Challenges. In 2017, we earned a scholarship placing in the top five percent of teams while investigating the effects of climate change on the US’s five coastal National Parks. In 2018, the team investigated the issue of food waste, placing in the top 6 teams out of 913, each earning a $1000 college scholarship and the opportunity to present our findings on an all-expenses paid trip to Jane Street Financial in New York City. Read our paper on the [M3 website](https://m3challenge.siam.org/sites/default/files/uploads/Team10278_Middlebury%20Union%20High%20School.pdf).

Sample Work (and some soon-to-be Publications)
======
  <ul>{% for post in site.publications %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
  
Talks
======
  <ul>{% for post in site.talks %}
    {% include archive-single-talk-cv.html %}
  {% endfor %}</ul>
  
<!-- Teaching
======
  <ul>{% for post in site.teaching %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
   -->

