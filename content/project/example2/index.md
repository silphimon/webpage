---
title: Hierarchical Bayesian non-parametric models to smooth longitudinal data.
summary: Methodological project aimed at extending hierarchical Dirichlet process mixture models to clustering grouped longitudinal data. Application in sport analytics.
tags:
- Non-parametric Bayes
- Hierarchical Dirichlet process mixture models
- Clustering
- Longitudinal data
date: "2021-11-06T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ""

# image:
#  caption: Photo by rawpixel on Unsplash
# focal_point: Smart

# links:
# - icon: twitter
#   icon_pack: fab
#  name: Follow
#  url: https://twitter.com/georgecushen
# url_code: ""
# url_pdf: ""
# url_slides: ""
# url_video: ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
# slides: example
---

Many modern statistical analyses involve variables best represented as curves, surfaces, or more general functions. Examples include biomarker trajectories, images, videos, genetic codes, and hurricane tracks. If data on such curves are available as measurements taken at irregular time points or locations that vary from subject to subject, the data are labelled as longitudinal data and the related analysis is labelled as longitudinal data analysis. Common goals in longitudinal data analysis are the: 

1) Characterisation of average or “typical” time course
2) Estimation of individual curves from noisy data
3) Characterising homogeneity and patterns of variability among curves, and identifying unusual ones
4) Assessing the relationships of shapes of curves to covariates

Many of these objectives entail smoothing of individual curves, and this is the primary focus of this project. In particular, the project investigates the construction of a smoothing model for clustered longitudinal data. 

The applied motivation for this work arises in sports analytics, where the interest is in describing and predicting the performance trajectory of an athlete throughout his/her career. Here the data (performance measured at sportive competition) for a professional athlete are seen as noisy measurements of an underlying smooth function. Such data may display some sort of seasonality, where here the term “seasonality” is used to indicate a time-dependent gathering of the observations.  We assume that, within a particular season, the performance on an athlete varies about a season-specific mean, namely, a season-specific and athlete-specific random intercept. It is reasonable to expect some degree of dependence for the average performance of an athlete across seasons, and further different athletes may exhibit similar season-specific average performances. In other terms, for each season, we may want to group together (cluster) athletes showing similar average performance within that season, then link clusters across different seasons to learn similarities/differences in performance.

To accomplish the goal above, the project leverages on hierarchical Dirichlet Process mixture models ([Teh et al., 2006](https://www.tandfonline.com/doi/abs/10.1198/016214506000000302)) and, more specifically, on its Chinese Restaurant Franchise representation for posterior computation. The topic of clustering grouped data has recently received attention in the literature (see, e.g., [Argiento et al., 2020](https://www.tandfonline.com/doi/abs/10.1080/01621459.2019.1594833?journalCode=uasa20)), and this project substantially entails the extension of [Argiento et al., 2020](https://www.tandfonline.com/doi/abs/10.1080/01621459.2019.1594833?journalCode=uasa20) to the longitudinal data case. 


## Meet your advisor(s)

This is a joint project with {{< mention "admin" >}} and {{< mention "[Prof. Raffaele Argiento](http://www.raffaeleargiento.it/)" >}} (Bergamo).

## FAQs

{{< spoiler text="Are there prerequisites?" >}}
This project is intended for MSc students with a strong quantitative background. Students must have taken the course Bayesian Statistics (MAT0070) for the MSc in Stochastics & Data Science, or equivalent. 

Work on this project is computationally demanding. The project involves (a good amount of) computing, and good knowledge of the R programming language is a must. Code will be made available to the interested student but will require some modifications/extensions and possibly some debugging.  The backbone sampler is implemented in C++, whilst the analysis of results can be carried out in R. Familiarity with C++ is not required, but certainly does speed up the work on this project. 

{{< /spoiler >}}

{{< spoiler text="Are there any references?" >}}
To become more familiar with this topic, please refer to:

Argiento, R., Cremaschi, A., & Vannucci, M. (2020). [Hierarchical normalized completely random measures to cluster grouped data](https://www.tandfonline.com/doi/abs/10.1080/01621459.2019.1594833?journalCode=uasa20). Journal of the American Statistical Association, 115:529, 318-333.

Montagna, S. & Hopker, J. (2018). [A Bayesian Approach for the Use of Athlete Performance Data Within Anti-doping](https://www.frontiersin.org/articles/10.3389/fphys.2018.00884/full),  Frontiers in Physiology, 9:884.

Teh, Y. W., Jordan, M., Beal, M., & Blei, D. (2006). [Hierarchical Dirichlet processes](https://www.tandfonline.com/doi/abs/10.1198/016214506000000302). Journal of the American Statistical Association, 101, 1566-1581.

A more extensive list will be shared with the interested student.
{{< /spoiler >}}

{{< spoiler text="How long do I need to complete this project?" >}}
This is difficult to say in general terms as it depends on the general standing of the student (e.g., background, motivation, remaining exams, other commitments, etc.). However, we expect that several months of work will be needed in total. The student will first need to become familiar with the methods and sampler, the data, then implement the analyses on the shotput data. 
{{< /spoiler >}}

