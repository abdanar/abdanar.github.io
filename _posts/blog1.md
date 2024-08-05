---
layout: post
title: Compartmental models in mathematical epidemiology
date: 2024-01-03 11:12:00-0400
description: an example of a blog post with table of contents
tags: project
giscus_comments: true
related_posts: false
toc:
  beginning: true
---

## Introduction

It will be better if we define some terminologies in epidemiology before we start modeling. Even though there are many things to consider when it comes to the concepts of epidemiology, I will give the necessary definitions that are needed to understand the modeling covered in this paper. Let us start with a word from the title of the talk. What is epidemiology? Epidemiology is the study of the determinants, occurrence, and distribution of health and disease in a defined population. Note that the terminology is used for the human population here. If a defined population is an animal population, then the study is called epizootiology (or epizoology). Here, we are going to consider an epidemic; therefore, let us give a definition. According to the Cambridge Dictionary, an epidemic is the appearance of a particular disease in a large number of people at the same time (epizootic for animal populations). We will examine the mathematical modeling of infectious diseases so there are certain words to know their meanings, allowing us to understand the assumptions made for the models.  The following meanings for words are taken from 'A Dictionary of Epidemiology' by Miquel Porta, the only dictionary I found for Epidemiology. A host is a person or other living animal, including birds and arthropods, that provides subsistence or lodgment to an infectious agent under natural conditions. A susceptible is a member of a population at risk of becoming infected by a disease. I think this is enough for an undergraduate mathematics student, like myself, at least to start the topic. Please note that as the cases become complex, more terminology will be needed, and if needed, I will add the necessary ones.

## Disease progression

In the reference book, it was stated the objective of a mathematical model of an infectious disease is to describe the transmission process of the disease. The transmission is the passage of a pathogen from an infectious individual to the population of susceptibles through modes of transmission, such as airborne, droplet transmission, and direct or indirect physical contact. We will observe that there will be changes in mathematical models depending on the means of transmission. However, we now focus on the disease progression, one of the most important aspects to consider when mathematically modeling the disease.


The figure \ref{Fig1} clearly illustrates disease progression. There is no need to define the latent, incubation, and infectious periods, as they are clearly shown in the figure. Please note that the lengths of the latent, incubation, and infectious periods, as well as the ways they overlap, vary for different diseases. For example, the incubation period for ebola is shorter than the latent period, while for measles, the incubation period is longer than the latent period. (For detailed information, please refer to 'Epidemic Modelling – Some Notes, Maths, and Code' by Simon Dobson, if you are interested.) It is crucial to examine the progression of a specific disease because the model changes. For example, in some diseases where the incubation period is longer than the latent period, individuals remain asymptomatic, meaning they can infect others without showing any symptoms. It is essential to consider this scenario, as it significantly changes the model, a topic that will be discussed in more detail in the SEIR model.

## Compartmental models

To understand the idea of modeling the disease, let us consider the simplest case. Assume a constant number of host population (see Figure \ref{Fig2}). The dots in the figure represent humans in the population.

When asked to model, the first thing that comes to our minds is to split the population into three groups: susceptibles, infected, and recovered. I clearly show the groups different colors, blue, red and green (see Figure \ref{Fig3}). What we are interested in is knowing the number of people in each group at any given time. It is straightforward to see that as people come into contact, the numbers in each group change. Let us discuss the concept known as compartmental models for infectious diseases, which essentially involves the same principles we have been applying.

The host population is partitioned into mutually exclusive groups, referred to as compartments, based on the nature of the disease. Let us denote 


Here, we are examining the simplest compartmental model, which is known as the SIR model. We illustrate the transmission process using the diagram, called a transfer diagram.(see Figure \ref{fig4})

Recall that our aim is to obtain the number of hosts in each compartment at any given time $t$. We denote the numbers in each compartment by $S(t)$, $I(t)$, $R(t)$. We can construct a compartmental model by considering the net change in the number of individuals in each compartment in an interval $[t, t+\Delta t]$.

\begin{align*}
        \Delta S(t) &= \text{new susceptibles} + \text{transfer from } R- \text{new infections} - \text{removal from } S\\
        \Delta I(t) &= \text{new infections} - \text{transfer into } R - \text{removal from } I\\
        \Delta R(t) &= \text{transfer from } I - \text{transfer into } S - \text{removal from } R
\end{align*}
If we divide both sides of the above equations by $\Delta t$ and let $\Delta t \to 0$, we obtain the following differential equations.
\begin{align}
    S^{\prime}(t) &= \text{influx of new susceptibles} + \text{transfer rate from } R -\text{incidence rate} - \text{removal rate from } S\notag\\
    I^{\prime}(t) &= \text{incidence rate} - \text{transfer rate into } R - \text{removal rate from } I\label{eq1}\\
    R^{\prime}(t) &= \text{transfer rate from } I - \text{transfer rate into } S -\text{removal rate from } R\notag
\end{align}
To determine the right-hand side of the system of ODEs, assumptions for the infectious disease should be provided. Then, using these assumptions, we can define the right-hand side.

## Kermack-McKendrick model

As mentioned earlier, the model is constructed based on assumptions or hypotheses. Consider the following hypothesis about the transmission process of an infectious disease and its host population.
1. Transmission occurs horizontally through direct contact between hosts.
2. Mixing of individual hosts is homogeneous. In particular, the incidence rate can be expressed as $\lambda I(t)S(t)$, where $\lambda$ is called the \textit{transmission coefficient}.
3. Rate of transfer from a compartment is proportional to the population size of the compartment. For instance, the recovery rate can be written as $\gamma I(t)$, for a rate constant $\gamma$.
4. Infected individuals become infectious upon infection with no latency period.
5. There is no loss of immunity and no possibility of reinfection.
6. There is no input of new susceptibles and no removal from any compartments.

Notice that assumption 6 implies that the total host population remains constant. Even though we have considered assumptions that impose certain restrictions, these assumptions are plausible for a disease spread within the student population on a campus. When all the terms are substituted in \eqref{eq1}, we obtain the following system of differential equations.

\begin{align*}
    S^{\prime}(t) &= -\lambda IS,\\
    I^{\prime}(t) &= \lambda IS - \gamma I,\\
    R^{\prime}(t) &= \gamma I,
\end{align*}
with initial conditions
\begin{equation*}
    S(0) = S_{0}, \quad I(0) = I_{0}, \quad R(0) = 0.
\end{equation*}


This system of ordinary differential equations is called the Kermack-McKendrick epidemic model (the transfer diagram for the model is given in Figure \ref{fig5}).


In the derived model, the functions $S(t)$, $I(t)$, and $R(t)$, as well as the model parameters $\lambda$ and $\gamma$, are nonnegative, given that the functions $S(t)$, $I(t)$, and $R(t)$ denote the number of people. In addition, some observations can be made without solving the system. Let us denote the total host population by $N(t)$. Since we assume that the total host population is constant, then $N(t) = S_0 + I_0$. As $\lambda$, $S$, and $I$ are nonnegative, it is easy to notice that $S'(t) \leq 0$, implying that $S(t)$ is a decreasing function. We have defined the epidemic, but can we ascertain the conditions under which the epidemic occurs by examining this model? Yes, we can. In the model, we have the differential equation given by

\begin{equation}
\label{eq2}
    I^{\prime}(t) = I(\lambda S - \gamma). 
\end{equation}

When defining an epidemic, we state that it occurs when a large number of people are affected simultaneously. Alternatively, we can express that an epidemic occurs when there is a rapid increase in the number of infectious individuals. Mathematically speaking, this implies that an epidemic occurs when $I'(t) > 0$. By using the equation \eqref{eq2}, we observe that this occurs when $\lambda S - \gamma > 0$, or $S > \frac{\gamma}{\lambda}$. As we have observed that $S(t)$ is a decreasing function, it follows that $S_{0} > \frac{\gamma}{\lambda}$. Therefore, we conclude that an epidemic occurs if $S_{0} > \frac{\gamma}{\lambda}$. This phenomenon is known as threshold phenomena, and a threshold value $\frac{\gamma}{\lambda}$ is called the critical community size.

One may wonder how we arrive at the terms $\lambda IS$ and $\gamma I$ in the model. This question will be addressed in the next sections.

## Transfer rates

The model we have discussed assumes proportional transfer rates between compartments. However, our assumption that the recovery rate is in proportion to the size of the infectious population is by no means universal. Let us understand what it means for transfer rates to be proportional.

Let us consider a general compartment, denoted as $C$, with a total population size of $N(t)$. Individuals in this compartment exit at a rate of $rN(t)$, where $r$ is a positive constant. 

Then, we have the following initial value problem.
\begin{equation*}
    N^{\prime}(t) = -rN(t), \quad N(0) = N_{0}.
\end{equation*}
The solution to this problem is 
\begin{equation}\label{eq3}
    N(t) = N_{0}e^{-rt}, \quad \text{or }\quad  e^{-rt} = \dfrac{N(t)}{N_{0}}.
\end{equation}
The equality \eqref{eq3} shows that $e^{-rt}$ is the fraction of the host population that remains in compartment $C$. In probabilistic terms, it represents the probability of an individual being in $C$ at time $t$. As our focus is on the population transfer out of $C$, we consider
    \begin{equation*}
    F(t;r) = 
    \begin{cases}
        1-e^{-rt},& \quad t\geq 0,\\
        0,& \quad t<0.
    \end{cases}
\end{equation*}
This gives us the fraction of the population that has left compartment $C$ during the time period $[0, t)$, or the probability of an individual who has left compartment $C$ during $[0, t)$. If we denote $X$ as a random variable representing the \textit{residence time} of an individual in compartment $C$, then
\begin{equation*}
    F_{X}(t) = p(X\leq t).
\end{equation*}
It is clear to see that $F(t; r)$ is the cumulative distribution function of the exponential distribution. So, the residence time of an individual in compartment $C$ follows an exponential distribution. We can also write the probability density function for the random variable $X$.
\begin{equation*}
    f(t;r) = 
    \begin{cases}
        re^{-rt},& \quad t\geq 0,\\
        0,& \quad t<0.
    \end{cases}
\end{equation*}
The probability density function $f(t; r)$ shows the proportion of individuals with residence time $t$. We can also find the expected value of $X$, which gives us the \textit{mean residence time}.
\begin{equation*}
    E[X] = \int_{-\infty}^{\infty}tf(t)\,dt = \dfrac{1}{r}.
\end{equation*}
For transfers from compartment $I$ to $R$, the residence time is the period between the time of infection and the time of recovery, which is the \textit{infectious period}. Then the infectious periods of individuals follow an exponential distribution.
\begin{equation*}
    F(t;\gamma) = 
    \begin{cases}
        1-e^{-\gamma t},& \quad t\geq 0,\\
        0,& \quad t<0,
    \end{cases}
\end{equation*}
where $\frac{1}{\gamma}$ is the \textit{mean infectious period}. Similarly, for transfers from compartment $R$ to $S$, the residence time is the \textit{immune period} during which recovered individuals are protected from reinfection. Then the immune periods of individuals follow an exponential distribution.
\begin{equation*}
    F(t;\delta) = 
    \begin{cases}
        1-e^{-\delta t},& \quad t\geq 0,\\
        0,& \quad t<0,
    \end{cases}
\end{equation*}
where $\frac{1}{\delta}$ is the \textit{mean immune period}.

We have seen that if we assume the proportional exit rate, then we have an exponential distribution for the residence time of an individual in a compartment. But how do we derive the model equations when the infectious periods of individuals follow the distribution $F(t)$? Let us derive the model equations when the infectious periods of individuals follow the distribution $F(t)$. Notice that the change in assumption for the infectious period does not impact the equation for $S(t)$ in the simple SIR model we have shown. Based on this assumption, we will re-derive the equations for $I(t)$ and $R(t)$. Let $F_X(t)$ be the probability distribution function for residence time $X$. Then,
\begin{equation*}
        G(t) = 1-F_{X}(t) = P(X>t).
\end{equation*}
is the associated \textit{survival function}. The function $G(t)$ gives us the fraction of the population that has remained in the compartment during the time period $[0, t)$, or the probability of an individual who has remained in the compartment during $[0, t)$. For any given time $\tau > 0$, $G(t - \tau)$ is the fraction of individuals who became infected at time $\tau$ and are still infectious at time $t$ ($t > \tau$). Therefore, the number of people infected at time $\tau$ and remaining infectious at time $t$ is given by
\begin{equation*}
    \lambda I(\tau)S(\tau)G(t-\tau).
\end{equation*}
Then we can find the number of people accumulated in compartment $I$ since $\tau = 0$ is
\begin{equation*}
        I(t) = I_{0}(t) + \int_{0}^{t}\lambda I(\tau)S(\tau)G(t-\tau)\,d\tau,
\end{equation*}
where $I_0(t)$ is the number of people who are already infected at $\tau = 0$ and remain infectious at time $t$. Similarly, we can also obtain equation for compartment $R$.
\begin{equation*}
         R(t) = R_{0}(t) + \int_{0}^{t}\lambda I(\tau)S(\tau)(1-G(t-\tau))\,d\tau.
\end{equation*}
When $F(t) = 1 - e^{-\gamma t}$, we obtain
\begin{equation*}
    I(t) = I_{0}(t) + \int_{0}^{t}\lambda I(\tau)S(\tau)e^{-\gamma (t-\tau)}\,d\tau, \quad I_{0}(t) = I(0)e^{-\gamma t}.
\end{equation*}
Once the derivative is taken with respect to $t$, we get
\begin{equation*}
    I^{\prime}(t) = I^{\prime}_{0}(t) + \dfrac{d}{dt}\int_{0}^{t}\lambda I(\tau)S(\tau)e^{-\gamma (t-\tau)}\,d\tau, \quad I^{\prime}_{0}(t) = -\gamma I_{0}(t).
\end{equation*}
Let us use the Leibniz integral rule for differentiation above to obtain
\begin{align*}
    I^{\prime}(t) &= I^{\prime}_{0}(t) + \lambda I(t)S(t) -\gamma \int_{0}^{t}\lambda I(\tau)S(\tau)e^{-\gamma (t-\tau)}\,d\tau = \\
    &= -\gamma I_{0}(t) + \lambda I(t)S(t) -\gamma \int_{0}^{t}\lambda I(\tau)S(\tau)e^{-\gamma (t-\tau)}\,d\tau =\\
    &= \lambda I(t)S(t) -\gamma \left(I_{0}(t)+\int_{0}^{t}\lambda I(\tau)S(\tau)e^{-\gamma (t-\tau)}\,d\tau\right) =\\
    &=\lambda I(t)S(t) -\gamma I(t).
\end{align*}
Similarly, we can obtain
\begin{equation*}
    R^{\prime}(t) = \gamma I(t).
\end{equation*}
We have re-derived the equations for $I(t)$ and $R(t)$ in the SIR model discussed earlier.

## Disease incidence



