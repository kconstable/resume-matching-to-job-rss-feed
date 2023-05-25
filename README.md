# Resume Optimizstion to Job Feed
In this project I scrape a job search feed and determine the fit to my resume and cover letter to each job posting using natural language processing. The 'fit' between my resume + cover letter to the job description is determined via three methods;
1. Keyword Analysis
2. Similarity Scoring
3. Generative Text Summary Comparisions

## Job Feed Scapping
I used the job search feed on [workopolis](https://www.workopolis.com/jobsearch/find-jobs?ak=data%20science%20-intern%20-co-op&l=Toronto%2C%20ON&sr=10&t=-1&mip=%24110%2C000&jt=fulltime&job=hWy0ea16-UMEAUzyNlvXuBmpMoyLsq-eKQFOamD-I625DcsvfyJLaPoYr3hHTpYO) as a source of data science jobs to compare to my resume+cover letter. The Beautiful Soup library was used to scrape the left navigation column to click through the feed pagination, extract the job link, open the job description and extract the job text. 
![work-1](https://github.com/kconstable/resume-matching-to-job-rss-feed/assets/1649676/169417cc-9dab-47e0-81a6-513d770fdb17)


## Resume Matching to Job Feed
### Keyword Comparision
To compare keywords, a list of common skills was compiled from a cross-secion of data science job postings. The list was then used to count the frequency of those skills in each job posting and in my resume+cover letter and compared.  The plot below shows the difference in the number of mentions of each skill compared to a specific job posting.  In the matching keywords plot, a bar greater than zero indicates my resume+cover-letter mentions that skill more than the job posting, and a negative job indicates the job posting has a greater freqeucy.  The missing keywords plot shows keywords in the job posting which are abscent from my resume, and the Job Specific keywords plot counts keywords that are highlighted in the job posting  (if applicable)

The keyword coverage (# keywords in resume / # keywords in the job posting) is calculated and shown in the plot header, along with the weighted average keyword frequency.  This is a single score which calculates the sum of the differences in frequecy of each keyword, multiplied by the weight of thta keyword in the job posting.  A number larger than 1 indictes my resume has a higher overall frequecy of matches, while a score below 1 means there are some key keywords mentioned in the job posting that are not well represented in my resume. 
![plot-keywords-2](https://github.com/kconstable/resume-matching-to-job-rss-feed/assets/1649676/1449bba6-a6c0-4fe5-845b-6da89720c042)

### Similarity Scoring
![similaryity-plots-3](https://github.com/kconstable/resume-matching-to-job-rss-feed/assets/1649676/5beb0070-a8cb-44ea-8137-de582620be55)

### Summary of Match Results
![table-summary](https://github.com/kconstable/resume-matching-to-job-rss-feed/assets/1649676/6ec24502-ab0e-42b1-8d79-920d0c0309d1)
