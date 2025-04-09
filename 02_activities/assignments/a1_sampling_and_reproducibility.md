# ASSIGNMENT: Sampling and Reproducibility in Python

Read the blog post [Contact tracing can give a biased sample of COVID-19 cases](https://andrewwhitby.com/2020/11/24/contact-tracing-biased/) by Andrew Whitby to understand the context and motivation behind the simulation model we will be examining.

Examine the code in `whitby_covid_tracing.py`. Identify all stages at which sampling is occurring in the model. Describe in words the sampling procedure, referencing the functions used, sample size, sampling frame, any underlying distributions involved, and how these relate to the procedure outlined in the blog post.

Run the Python script file called whitby_covid_tracing.py as is and compare the results to the graphs in the original blog post. Does this code appear to reproduce the graphs from the original blog post?

Modify the number of repetitions in the simulation to 100 (from the original 1000). Run the script multiple times and observe the outputted graphs. Comment on the reproducibility of the results.

Alter the code so that it is reproducible. Describe the changes you made to the code and how they affected the reproducibility of the script file. The output does not need to match Whitby’s original blogpost/graphs, it just needs to produce the same output when run multiple times

# Author: Kristy Cheung

```
•	Sampling Stages and procedures:

1.	Primary Contact Tracing – Simple random sampling. Using the data frame ‘ppl’ infected individuals were assigned with randomly generated number between the the array of 0 and 1 using np.random.rand() function. Then, those individuals with random number below the set parameters ‘TRACE_SUCCESS’, which is equal to 0.2, will be assigned to be traced. These procedures are reflective of simple random sampling as an infected individual are randomly selected from the sample.

2.	Secondary contact tracing – Purposive sampling. First, the number of people traced per event was counted using .value_counts() function and assign as ‘event_trace_counts’. Then, for any events with greater than or equal to 2 individuals that are traced (= SECONDARY_TRACE_THRESHOLD), individuals that are infected will be selected for secondary contact tracing. These procedures are reflective of purposive sampling as only infected individuals in events with record of 2 or more successfully traced individuals will be selected for secondary contact tracing.

•	Sample size: 1000 people

•	Sample frame: People at wedding or brunch events.

•	Underlying distributions: 
    Binomial distribution, with 20% of sample population attended wedding and 80% of sample population attended brunches and 10% infection rate.

How these relate to the procedure outlined in blog post:

•	The procedures in the script closely align with the procedures outlined in the blog post in terms of sampling methods and how proportions of infections attributed to wedding was calculated.

Run the Python script file called whitby_covid_tracing.py as is and compare the results to the graphs in the original blog post. Does this code appear to reproduce the graphs from the original blog post? 

•	No, the code does not reproduce the graphs from the original post

Modify the number of repetitions in the simulation to 100 (from the original 1000). Run the script multiple times and observe the outputted graphs. Comment on the reproducibility of the results.

•	Outputted graphs are not reproducible. I ran the script for 4 times and each time, the distribution varies.

Alter the code so that it is reproducible. Describe the changes you made to the code and how they affected the reproducibility of the script file. The output does not need to match Whitby’s original blogpost/graphs, it just needs to produce the same output when run multiple times

•	I added the code: np.random.seed(1234) which will then recreate the same set of random number each time when running the simulation, thus ensuring reproducibility of the results.

```


## Criteria

|Criteria|Complete|Incomplete|
|--------|----|----|
|Altercation of the code|The code changes made, made it reproducible.|The code is still not reproducible.|
|Description of changes|The author explained the reasonings for the changes made well.|The author did not explain the reasonings for the changes made well.|

## Submission Information

🚨 **Please review our [Assignment Submission Guide](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md)** 🚨 for detailed instructions on how to format, branch, and submit your work. Following these guidelines is crucial for your submissions to be evaluated correctly.

### Submission Parameters:
* Submission Due Date: `23:59 - 09/04/2025`
* The branch name for your repo should be: `assignment-1`
* What to submit for this assignment:
    * This markdown file (a1_sampling_and_reproducibility.md) should be populated.
    * The `whitby_covid_tracing.py` should be changed.
* What the pull request link should look like for this assignment: `https://github.com/<your_github_username>/sampling/pull/<pr_id>`
    * Open a private window in your browser. Copy and paste the link to your pull request into the address bar. Make sure you can see your pull request properly. This helps the technical facilitator and learning support staff review your submission easily.

Checklist:
- [ ] Create a branch called `assignment-1`.
- [ ] Ensure that the repository is public.
- [ ] Review [the PR description guidelines](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md#guidelines-for-pull-request-descriptions) and adhere to them.
- [ ] Verify that the link is accessible in a private browser window.

If you encounter any difficulties or have questions, please don't hesitate to reach out to our team via the help channel in Slack. Our Technical Facilitators and Learning Support staff are here to help you navigate any challenges.
