# Resume Optimization to Job Feed
In this project, I scrape a job search feed and determine the fit of my resume and cover letter to each job posting using natural language processing. The 'fit' between my resume + cover letter to the job description is determined via three methods;
1. Keyword Analysis
2. Similarity Scoring
3. Generative Text Summary Comparisons

## Job Feed Scapping
I used the job search feed on [workopolis](https://www.workopolis.com/jobsearch/find-jobs?ak=data%20science%20-intern%20-co-op&l=Toronto%2C%20ON&sr=10&t=-1&mip=%24110%2C000&jt=fulltime&job=hWy0ea16-UMEAUzyNlvXuBmpMoyLsq-eKQFOamD-I625DcsvfyJLaPoYr3hHTpYO) as a source of data science jobs to compare to my resume+cover letter. The Beautiful Soup library was used to scrape the left navigation column to click through the feed pagination, extract the job link, open the job description, and extract the job text. 
![work-1](https://github.com/kconstable/resume-matching-to-job-rss-feed/assets/1649676/169417cc-9dab-47e0-81a6-513d770fdb17)

## Resume Matching to Job Feed
### Keyword Comparision
To compare keywords, a list of common skills was compiled from a cross-section of data science job postings. The list was then used to count the frequency of those skills in each job posting and in my resume+cover letter and compared.  The plot below shows the difference in the number of mentions of each skill compared to a specific job posting.  In the matching keywords plot, a bar greater than zero indicates my resume+cover-letter mentions that skill more than the job posting, and a negative job indicates the job posting has a greater frequency.  The missing keywords plot shows keywords in the job posting which are absent from my resume, and the Job Specific keywords plot counts keywords that are highlighted in the job posting  (if applicable)

### Similarity Scoring
### Summary of Match Results
I calculate a similarity score using the SPaCY library to quantify the similarity of the resume+cover-letter to each job posting.  The table below ranks each job posting based on fit-to-resume. The summary also shows the keyword coverage, and weighted keyword-score, and lists keywords in the job posting which are missing from the resume.
![table-summary](https://github.com/kconstable/resume-matching-to-job-rss-feed/assets/1649676/6ec24502-ab0e-42b1-8d79-920d0c0309d1)

We can visualize the resume match to each job posting in the plot below.  The similarity score is on the y-axis and depicted with a color scale, and the keyword coverage is on the x-axis. The size of each bubble represents the weighted keyword score.  We should have a better chance at applying for the jobs in the upper right corner of the plot which have the largest bubbles.  
![similaryity-plots-3](https://github.com/kconstable/resume-matching-to-job-rss-feed/assets/1649676/5beb0070-a8cb-44ea-8137-de582620be55) 


