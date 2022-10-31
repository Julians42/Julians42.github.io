---
title: "Seismology Research Exprience"
collection: portfolio
excerpt: 'Detailing my work with the Harvard and UWashington Seismology Groups<br/><img src='/images/all_j_photos/seismo-portfolio-pic.png' width = 500>'
---
Beginning spring 2020 I joined the Harvard Seismology group as a research assistant for a term-time position which ulimately expanded into a 15-month position across 2 part-time (20 hrs/week) appointments during Summer 2020 and Spring 2021 along with term-time research during Fall 2020. I following my PI Marine A. Denolle to the University of Washington during Spring 2021 during a gap semester to continue working on the projects. From owning my work in an inter-department collaboration, attending and sharing in weekly group meetings and seminars, and presentating at two fall seismology conferences (SCEC and AGU) I've experienced what research in a graduate lab is like.

## The BASIN Project
Both of the projects I worked on utilized Amazon's EC2 and S3 cloud computing and storage interfaces. Leveraging these tools allowed us to overcome challenges associated with storing, moving, and computing with hundreds of terabytes of seismological data. The first project involved roughly 20 TB of nodal data from sensors deployed in the Los Angeles basin. Using pair-wise comparisons (or cross-correlations) of the waveforms we derived estimates for the severity of expected groundmotion for a potential future San Andreas Fault area earthquake. We collaborated with a team at UC San Diego who were running numerical eathquake simulations to verify these findings. My role specifically was developing the script and cloud architecture to run the empirical cross-correlation calculations along with post-processing and plotting results, presented weekly at the project meeting.

### BASIN Products
This project resulted in a package, workflow, and empirical results for the validation. While the results certainly warant a paper, we did not collectively found the time. I produced a `Julia` package to run high-performance large-workflow seismology jobs on AWS, called [SeisCore.jl](https://github.com/Julians42/SeisCore.jl), that is publicly available. 


## C4: Comprehensive California Cross-Correlations
The second project scaled up the first by an order of magnitude, with a target of computing 20 years of cross correlations for all of California. With the goal of making high performance cloud computing both more accessible and reproducible, I developed a publicly-available [docker container](https://hub.docker.com/repository/docker/vtskier/download_iris) that can be deployed using AWS Batch to scrape the over 70 TB of raw waveforms from the FDSN in under 72 hours resulting in a 10x improvement in both cost and speed over a similar technique published in MacCarthy et al. 2020. The workflow for this project can be found at [C4-Project.jl](https://github.com/Julians42/C4-Project.jl)