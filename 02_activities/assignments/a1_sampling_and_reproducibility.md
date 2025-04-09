# ASSIGNMENT: Sampling and Reproducibility in Python

Read the blog post [Contact tracing can give a biased sample of COVID-19 cases](https://andrewwhitby.com/2020/11/24/contact-tracing-biased/) by Andrew Whitby to understand the context and motivation behind the simulation model we will be examining.

Examine the code in `whitby_covid_tracing.py`. Identify all stages at which sampling is occurring in the model. Describe in words the sampling procedure, referencing the functions used, sample size, sampling frame, any underlying distributions involved, and how these relate to the procedure outlined in the blog post.

Run the Python script file called whitby_covid_tracing.py as is and compare the results to the graphs in the original blog post. Does this code appear to reproduce the graphs from the original blog post?

Modify the number of repetitions in the simulation to 100 (from the original 1000). Run the script multiple times and observe the outputted graphs. Comment on the reproducibility of the results.

Alter the code so that it is reproducible. Describe the changes you made to the code and how they affected the reproducibility of the script file. The output does not need to match Whitby’s original blogpost/graphs, it just needs to produce the same output when run multiple times

# Author: Chelsey

```
1. ~
Initial Sampling:
The model begins with a defined population of 1,000 individuals, where 200 attend a wedding and 800 attend a brunch. This is structured using the following line of code:

events = ['wedding'] * 200 + ['brunch'] * 800

Infection Sampling:
From the total population, 10% are randomly selected to become infected. This results in approximately 20 infections from the wedding group and 80 from the brunch group, for a total of 100 cases — matching the proportions mentioned in the blog post. The random selection is performed using:

infected_indices = np.random.choice(ppl.index, size=int(len(ppl) * ATTACK_RATE), replace=False)
ppl.loc[infected_indices, 'infected'] = True

This uses uniform random sampling without replacement to assign infections.

Primary Tracing Sampling:
A fraction (20%) of the infected individuals are randomly chosen to be successfully traced. This is implemented via:

ppl.loc[ppl['infected'], 'traced'] = np.random.rand(sum(ppl['infected'])) < TRACE_SUCCESS

The np.random.rand() function generates a random value for each infected person to determine if they are traced.
With a seed set (e.g., np.random.seed(123)), the result might be something like:

False    86  
True     14

Secondary Tracing Based on Event Participation:
The model then performs a secondary tracing phase, where events are flagged if at least two traced individuals attended. In these cases, all infected individuals at those events are also marked as traced. This is executed using:

event_trace_counts = ppl[ppl['traced'] == True]['event'].value_counts()
events_traced = event_trace_counts[event_trace_counts >= SECONDARY_TRACE_THRESHOLD].index
ppl.loc[ppl['event'].isin(events_traced) & ppl['infected'], 'traced'] = True

This step biases the tracing process in favor of events with more initial traced cases.

Final Observations:
After running the full simulation with np.random.seed(123), the final count of traced infections might yield:

ppl['traced'].value_counts()

Resulting in 79 traced infections from brunch and 21 from weddings. This output is slightly different from the blog’s example, which lists 80 and 20, but still aligns closely due to inherent randomness in the sampling.

2. ~

Running the whitby_covid_tracing.py script as-is produces two histograms showing the proportion of infections and traced cases attributed to weddings across 1000 simulations. These results closely mirror the graphs in Whitby’s blog post, where the actual infections from weddings center around 0.2 (reflecting their 20% representation in the sample), while the traced cases skew higher—often between 0.3 and 0.5—demonstrating how weddings become overrepresented in contact tracing data. This visual and statistical pattern effectively supports the blog’s main point: contact tracing introduces bias by amplifying visibility for events where tracing happens to be more successful. While slight variations may occur due to the script’s use of random sampling without a fixed seed, the overall shape and message of the plots are consistent with those in the original blog post.

3.~

After modifying the number of simulation repetitions from 1000 to 100 and running the script multiple times, it becomes clear that the output histograms vary noticeably with each execution. This is due to the inherent randomness in the infection and tracing processes, especially given the smaller sample of repetitions, which increases the variability between runs. As a result, the shape, spread, and even the central tendencies of the histograms (particularly the traced distribution) can shift from one run to another. This demonstrates that without a fixed random seed, the results are not reproducible, and conclusions drawn from a single run may not be reliable. Reproducibility in this context would require either a larger number of repetitions or controlling the randomness to ensure consistent outputs.

4. ~
Code modified in .py file. The main component needed was:

np.random.seed(12)  - Modification to ensures reproducible results
results = [simulate_event(m) for m in range(100)] - Changed for the 100 simulation repititions

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
