+++
title = "thesis"

[extra]
hide_title = true
+++

# Thesis Introduction

Below is a reproduction of the introductory chapter of my thesis outlining my approach to statistics and contributions. This excerpt includes links to papers that form the basis of some thesis chapters. This chapter can be cited as:
- Hines O. J. (2023) Introduction. In *Assumption-lean inference for causal and statistical questions in the era of machine learning* \[Doctoral dissertation, London School of Hygiene and Tropical Medicine\].


## Background

Modern statistical theory is built on a framework of model based inference, where the targets of inference are the parameters indexing assumed semi-parametric statistical models[^1]. It is difficult to understate the impact that this theory has had on society (epidemiology, psychology, economics etc.), especially since the latter half of the 20th century when advances in computational technology have meant that data is more routinely collected, and the cost of computing increasingly intricate analyses has been significantly reduced. As human beings, we find parametric models relatively straightforward to reason about, with model parameters encoding different aspects of the data generating mechanism. For instance, the model parameters indexing generalised linear models can inform investigators about the main effect of an exposure on an outcome, modification of this main effect by other variables, or mediation of the main effect through other variables. Parameter interpretations of this type, however, are inherently ''causal'' in nature, but despite this, little regard was given to the causal nature of the statistical model for much of the development of modern statistics. Instead, causal reasoning was understood to be simply outside of the remit of statisticians, with deliberately non-causal language used to describe statistical results.

Over recent decades, a theory of causal inference has developed[^2] whereby a second ''causal model'' is specified alongside the statistical model. Formally, the causal model is a mathematical structure which encodes the assumed conditional independence relationships between the random variables of interest that is required to interpret model parameters ''causally''. Contrary to its name, the methods of ''causal inference'' are not able to infer whether one variable causes another or vice-versa, rather one might say that the goal of causal inference is to interpret the objects of ordinary statistical inference, in view of the assumed causal model. Indeed the algorithms and statistical machinery used in causal inference analyses are often identical to those used to make non-causal statements regarding association and correlation. Moreover, causal modelling relies on untestable causal assumptions, with domain-specific expert knowledge required to elicit and defend causal assumptions.

Philosophically speaking, the separation of the causal model and the statistical model is appealing since conditional independence assumptions that are made for the purposes of interpretation (the causal model) are distinct from those which encode a priori known parametric structure about the data-generating mechanism (the statistical model). Oftentimes, however, assumptions regarding the statistical model do not represent a priori known parametric structure, but instead are made either to facilitate inference or simplify model interpretability[^3]. For example, time-to-event analyses in medical research routinely assume Cox proportional hazards models for convenience and because hazard ratio parameters are (arguably) easy to interpret. This results in two main issues which arise when the statistical model is misspecified: firstly, different estimators of the same model parameter may converge to different results; and secondly, it is not so clear how the resulting (estimator dependent) estimates should be interpreted, even in the limit as sample size grows to infinity. Worse still, these problems persist even when model/variable selection strategies are used to mitigate the risk of model misspecification, not least because uncertainty due to model selection is rarely acknowledged.

To address these issues, it has become increasingly common to centre analyses around nonparametrically defined targets of inference, called 'estimands', instead of focussing on statistical model parameters[^4]. Like statistical model parameters, estimands can often be ascribed a causal interpretation under an assumed causal model, though the study of estimands remains interesting even in settings where this is not the case. The advantage of targeting a model-free estimand is that analysts can be more flexible in the modelling strategies used to estimate requisite statistical functionals, since the interpretation of the estimand does not rely on any particular form of the statistical model. In effect, this means that statistical models can be replaced with more flexible ''algorithmic machine learning models'' (e.g. lasso, neural networks, gradient boosting, random forests, ensemble learning etc.), which are routinely used for prediction tasks in the computer sciences.

Moreover, these developments are significant for the machine learning community, since complicated machine learning models, which may perform well in prediction tasks, are sometimes criticised as being 'black box' due to their lack of model interpretability[^5]. The nonparametric theory surrounding estimands therefore provides a valuable tool for explaining the broad trends which are encoded in machine learning prediction models.

The current PhD project sits at the intersection of the four aforementioned topics: statistical modelling, causal modelling, estimand based inference, and algorithmic machine learning, and makes several contributions as outlined below.

## Contributions

This PhD thesis consists of several self-contained chapters, intended to read like a series of thematically linked journal articles. This structure was chosen principally because this is the way that the field of statistics usually develops, by considering specific limited problems, with novel results communicated through standalone articles. Additionally, several of the chapters are in fact published (or pre-print) journal articles. Where this is the case, the associated publication is referenced according to the list of publications in the front matter of this thesis.

[Chapter 2](https://scholar.google.com/citations?view_op=view_citation&hl=en&user=7nqnc34AAAAJ&citation_for_view=7nqnc34AAAAJ:qjMakFHDy7sC) gives an introduction to causal modelling and outlines several common causal model structures which occur in the field of genetics and genetic epidemiology. The application area of genetic data is interesting, since it represents a field where parametric statistical modelling techniques are routinely used e.g. to parameterise the effect of a particular genetic variant on a physical trait, and to account for genetic cohorts with heterogeneous ancestry. We use causal directed acyclic graphs (DAGs) as a tool for representing causal assumptions and deriving implied independencies. Whilst the use of DAGs is common when discussing some genetic applications, such as Mendelian randomisation, we have not seen elsewhere similar discussions regarding genome wide association studies and ancestral confounding, with only limited DAG based discussions of selection biases in genetic cohorts. The main contribution of this chapter is therefore to consolidate these causal model structures and explain how they may be used to ascribe a causal interpretation to statistical model parameters.

[Chapter 3](https://scholar.google.com/citations?view_op=view_citation&hl=en&user=7nqnc34AAAAJ&citation_for_view=7nqnc34AAAAJ:d1gkVwhDpl0C) focusses on the problem of inferring natural direct and natural indirect effects, under standard causal assumptions, and assuming certain semi-parametric partially linear models. Natural direct and indirect effects are nonparametric estimands that arise in mediation analyses in epidemiology, psychometrics, and economics. They quantify the amount by which a 'mediating variable' transmits the main effect of an exposure on an outcome, and under common partially linear statistical model assumptions, respectively reduce to a single model coefficient and a product of two model coefficients. The latter product of coefficients makes inference in this context particularly challenging, and we use a so-called ''G-estimation strategy'' to address this inference problem in a new way. Our estimators demonstrate appealing robustness properties when parts of the model are misspecified and we make use of recent score-type testing results to test null effect hypotheses.

Whilst [Chapter 3](https://scholar.google.com/citations?view_op=view_citation&hl=en&user=7nqnc34AAAAJ&citation_for_view=7nqnc34AAAAJ:d1gkVwhDpl0C) evokes semi-parametric statistical models to infer nonparametric estimands, [Chapter 4](https://scholar.google.com/citations?view_op=view_citation&hl=en&user=7nqnc34AAAAJ&citation_for_view=7nqnc34AAAAJ:2osOgNQ5qMEC) demonstrates how estimand inference can be carried out in a model-free way, so long as the estimand is 'pathwise differentiable'. Such estimands usually permit efficient estimators that are amenable to data-adaptive/ machine learning estimation of requisite statistical functionals, representing a fundamental and revolutionary departure from parametric statistical modelling in terms of how data is analysed and results are interpreted. One of the main challenges in deriving efficient estimators is first to derive the estimand's 'pathwise derivative', also called its 'efficient influence function/curve'. The goal of [Chapter 4](https://scholar.google.com/citations?view_op=view_citation&hl=en&user=7nqnc34AAAAJ&citation_for_view=7nqnc34AAAAJ:2osOgNQ5qMEC) is to demystify estimand inference, with a particular focus on influence curve derivations, often regarded as somewhat of a dark art. We advocate a 'point mass contamination' method for influence curve derivation and rederive several literature influence curves using this approach. In later Chapters, we use this same method to derive efficient influence curves for new estimands.

[Chapter 5](https://scholar.google.com/citations?view_op=view_citation&hl=en&user=7nqnc34AAAAJ&citation_for_view=7nqnc34AAAAJ:UeHWp8X0CEIC) contains a proposal for a new estimand to quantify the importance of covariates in explaining heterogeneity in the effect of a binary treatment on an outcome. The proposed estimands are a novel contribution of the current thesis and relate analogous 'variable importance estimands' in nonparametric regression analysis to recent 'variance of treatment effect' estimands, which act as global measures of treatment effect heterogeneity. We assume a canonical causal model as found in the literature on (conditional) average treatment effects, making the proposed methods immediately applicable to e.g. both clinical trials data and observational 'real world' data.

One common feature of the proposed variable importance estimands, the regression variable importance estimands, and the variance of treatment effect estimand, is that they are all defined on a bounded support e.g. \[0,∞) or \[0,1\]. This makes subsequent inference challenging since the asymptotic normality of the estimator breaks down in finite samples when the true estimand value is close to the boundary of the support. This issue is addressed in Chapter 6, which contains a generic proposal for score based inference of nonparametric estimands, as opposed to the typical Wald type methods described in [Chapter 4](https://scholar.google.com/citations?view_op=view_citation&hl=en&user=7nqnc34AAAAJ&citation_for_view=7nqnc34AAAAJ:2osOgNQ5qMEC). Our proposal builds on ideas from 'targeted learning' (TMLE) and the score testing procedures considered in [Chapter 3](https://scholar.google.com/citations?view_op=view_citation&hl=en&user=7nqnc34AAAAJ&citation_for_view=7nqnc34AAAAJ:d1gkVwhDpl0C), and is shown to perform well in simulation studies in terms of confidence interval coverage.

Although the theory of model-free estimand based inference is most often applied to settings where the estimand is causally interpreted under a causal model, it is not necessary that the estimand is causally motivated. In [Chapter 7](https://scholar.google.com/citations?view_op=view_citation&hl=en&user=7nqnc34AAAAJ&citation_for_view=7nqnc34AAAAJ:Y0pCki6q_DkC) we present results for weighted derivative effect estimands, which have classically been studied in the econometrics literature in the context of single index models, though they remain equally applicable to epidemiological problems. These estimands consider how the conditional response surface of an outcome varies, on average, for small changes in the exposure. Traditional estimators are based on nonparametric kernel density estimators, however these introduce complicated biases as the number of the predictors grows. By considering nonparametric efficiency bounds, we derive an optimally weighted average derivative estimand and connect it to literature on so-called projection estimands in partially linear models. We propose a class of 'least squares estimands' containing the optimal one and derive efficient estimators under the model-free estimand inference framework, reviewed in [Chapter 4](https://scholar.google.com/citations?view_op=view_citation&hl=en&user=7nqnc34AAAAJ&citation_for_view=7nqnc34AAAAJ:2osOgNQ5qMEC). In Chapter 8, least-squares estimands, and other weighted derivative effect estimands, are ascribed a causal interpretation in terms of so-called stochastic interventions.

## Footnotes

[^1]: Likelihood based inference developed in the late 19th and early 20th century with pioneering work by Galton, Pearson, Fisher, Neyman, Cramer, Rao etc..

[^2]: Causal developments are discussed in [Chapter 2](https://scholar.google.com/citations?view_op=view_citation&hl=en&user=7nqnc34AAAAJ&citation_for_view=7nqnc34AAAAJ:qjMakFHDy7sC) with early work by Rubens, Pearl and others see e.g. Pearl (1986), Rubin (2005), Glymour (2006), Hernán and Robins (2020).

[^3]: Criticisms of this type can be found in Breiman (2001), van der Laan (2015), Vansteelandt and Dukes (2022).

[^4]: These ideas are codified in the 'Roadmap' by van der Laan and Rose (2011), Petersen and van der Laan (2014) and rely on results from nonparametric statistics, which we discuss in [Chapter 4](https://scholar.google.com/citations?view_op=view_citation&hl=en&user=7nqnc34AAAAJ&citation_for_view=7nqnc34AAAAJ:2osOgNQ5qMEC), see e.g. Pfanzagl and Wefelmeyer (1985), Pfanzagl (1990), Bickel et al. (1993).

[^5]: See e.g. Ribeiro (2016), Lundberg (2017) for proposals related to interpreting black-box predictions.

<details>
<summary>View references</summary>

## References

- Bickel, P. J., Klaassen, C. A., Bickel, P. J., Ritov, Y., Klaassen, J., Wellner, J. A., and Ritov, Y. (1993). *Efficient and adaptive estimation for semiparametric models*, volume 4. Johns Hopkins University Press Baltimore.
- Breiman, L. (2001). *Statistical modeling: The two cultures*. Statistical Science, 16(3):199–215.
- Glymour, M. M. (2006). *Using causal diagrams to understand common problems in social epidemiology*. In Methods in Social Epidemiology, 393–428. John Wiley and Sons.
- Hernán, M. A. and Robins, J. M. (2006). *Estimating causal effects from epidemiological data*. Journal of Epidemiology & Community Health, 60(7):578–586.
- Lundberg, S. M. and Lee, S.-I. (2017). *A unified approach to interpreting model predictions*. In Proceedings of the 31st international conference on neural information processing systems, 4768–4777.
- Pearl, J. (1986). *Fusion, propagation, and structuring in belief networks*. Artificial Intelligence, 29(3):241– 288.
- Petersen, M. L. and van der Laan, M. J. (2014). *Causal models and learning from data: Integrating causal modeling and statistical estimation*. Epidemiology, 25(3):418–426.
- Pfanzagl, J. and Wefelmeyer, W. (1985). *Contributions to a general asymptotic statistical theory*. Statistics & Risk Modeling, 3(3-4):379–388.
- Pfanzagl, J. (1990). *Estimation in semiparametric models*. In Estimation in Semiparametric Models, 17–22. Springer.
- Ribeiro, M. T., Singh, S., and Guestrin, C. (2016). *”Why Should I Trust You?” Explaining the Predictions of Any Classifier*. NAACL-HLT 2016 - 2016 Conference of the North American Chapter of the Association for Computational Linguistics: Human Language Technologies, Proceedings of the Demonstrations Session, 97–101.
- Rubin, D. B. (2005). *Causal inference using potential outcomes: Design, modeling, decisions*. Journal of the American Statistical Association, 100(469):322–331.
- van der Laan, M. J. and Rose, S. (2011). *Targeted Learning*, volume 27 of Springer Series in Statistics.
Springer New York, New York, NY.
- van der Laan, M. J. (2015). *Statistics as a science, not an art: the way to survive in data science*. Amstat News, 1.
- Vansteelandt, S. and Dukes, O. (2022). *Assumption-lean inference for generalised linear model parameters*. Journal of the Royal Statistical Society: Series B (Statistical Methodology), 84(3):657–685.

</details>