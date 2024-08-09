---
author_profile: true
title: CV
permalink: /cv/
toc: true
toc_sticky: true
toc_label: "CV"
toc_icon: "file-alt"
---

#### Employment

##### 2023-&nbsp;&nbsp;&nbsp;&nbsp;, Senior Cyber Platform Engineer, *[Department for Work and Pensions - Digital](https://dwpdigital.blog.gov.uk/about/){:target="_blank"}, homeworker*

Leading the integration of cloud-native data science applications at the Cyber Resilience Centre with a focus on security, automation, and best practices. Leveraging open source and inner source tools to drive organizational productivity and foster a collaborative engineering culture.

*   **Cloud-Native Application Development:** Architect and build cloud-based data science applications using Terraform, Docker, Python, AWS, and GitLab pipelines, focusing on scalability and performance.
    
    *   Build Terraform modules that implements a new ¨multi-user” architecture for our platform. It enables our team to **deploy new multi-user container services with seamless user management** through our organization-specific Microsoft EntraID applications
        
    *   **Refactorate our Flask application for multi-user authenticatio**n by implementating an authentication module that verifies [user claim signature in the HTTP header sent by the load balancer](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/listener-authenticate-users.html#user-claims-encoding).
        
*   **Security Automation & Best Practices:** Lead the improvement of our security posture and the quality of our development processes. Guide the team in adopting these standards.
    
    *   **Hardened our python and neo4j Docker Images** using Chainguard to reduce attack surfaces, ensuring secure container deployment.
        
    *   **Lead the design and implementation of our testing strategy** for our platform and support the implementation of app-specific test plans.
        
    *   Support the team in adopting the **configuration as code tool** [**GitlabForm**](https://gitlabform.github.io/gitlabform/) for managing GitLab repository settings, ensuring consistency and security across repositories.
        
    *   **Implement pre-commit hooks** for Terraform and application repositories, which enforce automating code formatting, linting, and static code analysis to enforce high coding standards.
        
    *   **Build new inner source Gitlab CI/CD components** for static and dynamic code analysis tools, code vulnerability scanners and dependency updates automation which are used in our CI/CD pipelines
        
*   **CI/CD Optimization:** Lead the rebuild of our CI/CD pipeline and our infrastructure for continuous deployment of secure, versioned container images.
    
    *   **Implement automatic version tagging for our application repositories** based on the [release-please open source project](https://github.com/googleapis/release-please) and [c](https://github.com/googleapis/release-pleasec)[onventional commit messages](https://www.conventionalcommits.org/en/v1.0.0/), which automatically generates a version release Merge Requests in our app repostitories
        
    *   **Rebuild our CI/CD pipeline** to automatically trigger gitlab jobs for tagging Docker images with the current release version and pushing them to ECR, when a GitLab tag is created.
        
    *   Rebuild Terraform modules for our platform to support **versioned Docker containers**, allowing precise control over app versions deployed in our AWS environments.
        
*   **Collaboration & Knowledge Sharing:** Actively contributed to the team's knowledge base by sharing best practices and supporting colleagues in adopting secure, efficient development workflows.
    
    *   **Led initiatives to knowledge-sharing sessions** with the team on cloud-native development and security best practices.
        
    *   **Pair programming** sessions with junior team members to support them in adopting efficient development workflows
        
    *   **Mentor** for junior team members and as part of the cross-government mentoring programme \`Catapult\` which promotes social mobility

##### 2022-2023, Software Engineer, *[Department for Work and Pensions - Digital](https://dwpdigital.blog.gov.uk/about/){:target="_blank"}, Newcastle*
As a software engineer in a cross-functional Agile team, I played a key role in the development and deployment of a prototype cloud-based AI solution designed to extract insights from handwritten letters sent to DWP services. My contributions focused on both AI model optimization and cloud infrastructure deployment, with a strong emphasis on coding standards and best practices.

*   **AI Model Optimization:** Led the development of the AI component by creating a comprehensive test dataset and fine-tuning the labels and thresholds used in our zero-shot classification model, based on the [BART-large-MNLI model](https://huggingface.co/facebook/bart-large-mnli). This optimization significantly improved the model's accuracy in identifying relevant categories of vulnerable persons.
    
*   **Cloud Infrastructure & Deployment:** Build the Infrastructure and AI solution on Amazon SageMaker, utilizing the AWS Cloud Development Kit (CDK) to automate infrastructure provisioning.
    
*   **Serverless Architecture Implementation:** Developed and deployed serverless services using AWS Lambda with AWS CDK, employing both Python and TypeScript. This approach enhanced the solution’s scalability and reduced operational overhead.
    
*   **Python Coding Standards & CI/CD Integration:** Spearheaded the implementation of Python coding standards across the team and the organisation, integrating these standards into the CI/CD pipelines.


##### 2021-2022, R&D Software Developer, *[OSE Engineering](http://ose-engineering.fr/){:target="_blank"}, France*
Led the development of innovative software prototypes with a focus on both front-end and back-end technologies, and best practices in software development.

*   **Full-Stack Development:** Managed the full-stack development of a web application for controlling a fleet of [TwinswHeel](http://www.twinswheel.fr/) delivery robots, using JavaScript (cytoscape.js) and Django.
    
    *   Implemented key functionalities such as mission design, robot control via WebSocket, and remote operation through WebRTC, ensuring high performance and reliability.
        
*   **Python Development:** Developed a Python package for solving the electric vehicle routing problem, incorporating interactive map visualizations with Folium/Leaflet.js.
    
    *   Created comprehensive documentation and example notebooks to support the package, promoting its use across the organization.
        
*   **Best Practices & Developer Advocacy:** Initiated and authored an internal guide for Python software development best practices, covering project structure, meaningful code, documentation, testing strategies, and continuous integration.
    
    *   Advocated for and facilitated the adoption of these practices across teams, contributing to a culture of high-quality, maintainable software development.

##### 2019-2021, Research Scientist, *[National Oceanography Centre](https://noc.ac.uk/){:target="_blank"}, Southampton*
Analysis of multiple ocean & atmosphere datasets (structured and unstructured) to characterise the physical processes 
at work in the North Atlantic Ocean (poleward heat fluxes)
+ Identified origins of trends and patterns observed in flux variability (cross-correlation analysis, cluster analysis)
+ Developed methods (e.g. Monte Carlo) to reduce uncertainties on heat fluxes
+ Trained and led support scientists and PhD student to data processing and data analysis methods using Matlab, Python and Git

##### 2014-2018, Research Project Scientist, *[Scottish Association for Marine Science](https://www.sams.ac.uk/){:target="_blank"}, Oban*
Characterisation of the variability of North Atlantic circulation from ocean observations
+ Planned, executed and led fieldwork (transatlantic research cruises, robotic missions)
+ Developed reproducible workflow for the data processing of robotic data with the development of a matlab toolbox.
+ Designed new methods to characterise the ocean heat transport from new observations (gridding of irregular datasets, objective mapping, spectral analysis, Monte Carlo)
+ Led and published reports and research articles on the data obtained from field programmes

##### 2013–2014, Postdoctoral Associate, *[LOCEAN](https://www.locean-ipsl.upmc.fr){:target="_blank"}, Paris*
Characterisation of the spatio-temporal scales relevant for the winter mixing of the ocean
+ Identified principal mode of variability of ocean currents using dimension reduction methods.
+ Detection of coherent eddy patterns in time-series using wavelett analysis.

##### 2010–2013, PhD Fellow in Ocean Physics, *[CEFREM](https://cefrem.univ-perp.fr/){:target="_blank"}, Perpignan*
Analysis of multi-platform observations to study of the impact of episodic events (storm and winter mixing) 
on the ocean circulation and the long-term evolution of its properties
+ Data gathering, cleaning and exploration of oceanic profiles (>200k), including quality control procedures 
(cross-calibration,outliers), metadata collection and descriptive statistics
+ Analysed spatio-temporal variability of ocean mixing (covariance and time-series analysis)
+ Identified spatial regions with similar seasonal cycle using a k-mean cluster analysis

<br/>

#### Certifications
+ 2024, [GIAC Cloud Security Automation Certification (GCSA)](https://www.credly.com/badges/3932cedd-793a-4103-a00f-3be346e8fd8d)


<br/>

#### Education
+ 2010–2013, PhD in Ocean Physics, *CNRS, Perpignan*
+ 2008–2010, MSc, Atmospheric and Oceanic Physics, *Université Pierre et Marie Curie, Paris*
+ 2005-2008, BSc, Maths-Physics-Chemistry, *Université de Strasbourg*

<br/>



#### Technologies and Languages
##### Python Libraries
NumPy, Pandas, Xarray, Matplotlib, Holoviews, scikit-learn, networkx, Django, sphinx, pytest, pip
##### Technologies
Linux, Terraform, Docker, AWS, ECS, Git, gitlab-CI, AWS CDK, Jupyter, Websocket, WebRTC
##### Other Languages
TypeScript/JavaScript, Shell, HTML, CSS, MATLAB, Markdown, LATEX, SQL
##### Analytical Skills
  + Statistics: Covariance, Cross-correlation, Confidence intervals, Monte Carlo methods
  + Time-series: Spectral & Wavelett analysis, auto-correlation, detection of patterns & trends
  + Spatial: Geostatistics, Kriging, Objective Analysis
  + Supervised and Unsupervised Learning: Classification, Regression, Clustering

  
#### Experience with Python
I mostly use Python as a procedural programming and objected-oriented programming language. I love learning new python patterns 
and write “pythonic” code. For example, when it is suited, I like using assertions, decorators, _args_ and _*kwargs_ parameters, 
NamedTuples and Data Classes, ABC Classes, dictionary, list comprehensions, or generator expressions.

When I am writing code, I follow the [PEP8 guidelines](https://peps.python.org/pep-0008/) and software engineering principles from Robert C. Martin’s book [Clean Code](https://github.com/lhoupert/clean-code-python){:target="_blank"}, 
such as writing code that explains itself and is easy to read, writing bug repellent code, follow DRY and SOLID principles and working with design patterns.

I am also documenting the project continuously by creating markdown or reST files and writing docstrings for all the main functions, 
classes and modules developed in the project. Then I use [Sphinx](https://www.sphinx-doc.org/en/master/){:target="_blank"} to automatically extract docstrings and compiles them into 
a well-structured and easily readable HTML documentation.

I like to use the [Pytest](https://docs.pytest.org){:target="_blank"} framework for my unit and functional tests.

<br/>

#### Personal Skills, learned during my academic career
##### Leadership
  + Responsible for the data acquisition, processing & storage for the UK research program [UK-OSNAP](https://www.ukosnap.org)
  + Supervised and trained MSc and PhD students to data analysis methods in oceanography
  + Organiser of the Oceanography and Climate seminars at the National Oceanography Centre

##### Communication
  + Published 27 scientific articles in peer review journals ([>700 citations](https://publons.com/researcher/Y-5796-2019/)), 7 reports
  + Delivered regular presentations in international and national conferences (60 incl. 12 invited)
  + Engagement with public and stakeholders on climate change

##### Teamwork
  + Inter-disciplinary and international scientific collaborations with physicists, chemists, biologists, geologists, statisticians from UK, US, Netherlands, France, Germany and China
  + Close collaborations with scientists, technicians, IT-experts and mariners. particularly during research cruises


<br/>

#### Fieldwork
+ 12 oceanographic cruises, 200 days at sea in the North Atlantic and in the Mediterranean.
Planned and led fieldwork activities, liaise with mariners, cruise reports redaction
+ 9 ocean glider missions (underwater robot) [2014-2018]: piloting, data processing and analysis
