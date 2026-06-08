# Technical Challenge — Sourcing Analysis with AI

## Overview
This project analyzes a fictional sourcing and recruitment dataset to identify which sourcing strategies convert best, what candidate signals indicate a higher chance of advancing, when it is worth persisting with a candidate, and when conversion probability is low. The analysis combines funnel diagnostics, channel-level comparisons, practical recruiter recommendations, and a simple AI model used to support prioritization decisions.

The dataset contains 601 sourced candidates, with progression tracked across response, screening, interview, test, offer, and hire stages. The overall goal is not only to describe performance, but to turn the data into actions recruiters can apply in day-to-day pipeline management.

## Approach
The analysis was structured in four layers. First, a funnel analysis measured drop-off between stages to identify the largest leaks in the process. Second, sourcing channels were compared on response, screening, interview, offer, and hire rates. Third, behavioral and process signals such as response time, assessment scores, and stage progression were interpreted to determine where persistence is worthwhile. Fourth, a simple machine learning model was used to estimate which variables were most associated with hiring outcomes.

This approach was chosen because it balances business relevance and technical clarity. A recruiter or talent leader needs more than a descriptive dashboard; they need to know where to invest effort, where to stop spending time, and how to use AI responsibly to support prioritization.

## Funnel Analysis
The funnel starts with 601 sourced candidates, of whom 408 responded, 308 passed screening, 234 advanced through the first interview, 201 took a test, 62 received an offer, and 49 were ultimately hired. This shows that the process loses talent steadily at every stage, with especially important losses between sourcing and response, and again between test completion and offer.

These numbers suggest that two operational questions matter most. The first is whether recruiters are reaching the right people and engaging them quickly enough to secure response. The second is whether the team is being selective early enough so that later-stage effort is concentrated on candidates with a stronger probability of offer and hire.

## Channel Performance
Channel analysis shows meaningful differences in conversion quality. GitHub had the highest observed hire rate at 11.0 percent, followed by Inbound at 10.1 percent and Hunting at 9.3 percent. Banco de Talentos and LinkedIn both produced hire rates of 8.8 percent and 8.6 percent respectively, while Evento and Indicação had the weakest final conversion rates in this dataset, at 4.9 percent and 4.7 percent.

Inbound and Banco de Talentos also showed relatively strong response rates, at 79.7 percent and 75.0 percent, while LinkedIn and Hunting were lower at 63.0 percent and 64.0 percent. GitHub stood out as a balanced channel because it combined solid response levels with the strongest final hiring outcome.

One important nuance is that Indicação had the highest average technical score, at 80.4, but did not translate that quality signal into strong hiring conversion. This suggests that technical strength alone is not enough; process speed, fit alignment, and downstream decision quality also matter.

## Signals of Advancement
The dataset suggests that early responsiveness is a meaningful signal. Channels with faster average response time, such as Banco de Talentos and Inbound, tended to support stronger early-stage conversion. In practice, candidates who engage quickly are easier to move through the process, easier to schedule, and less likely to stall the funnel.

Assessment performance also matters, but in combination with process signals. The evidence indicates that candidates with stronger technical, behavioral, and manager scores are more likely to remain viable deeper into the funnel, yet high scores alone do not guarantee hire if timing, motivation, or business constraints interfere.

Recruiters should therefore evaluate advancement using a combination of variables: source channel, speed of response, quality of screening outcome, and consistency across evaluation stages.

## When Persistence Is Worth It
Persistence tends to be worthwhile when a candidate has already signaled intent and capability. Candidates who responded, cleared screening, and maintained acceptable evaluation scores should remain in active follow-up even when there are short delays caused by scheduling, competing processes, or internal timing.

This is especially true for candidates from higher-performing channels such as GitHub, Inbound, and Hunting. When those profiles also show fast response behavior and steady progression, the incremental effort required to keep them warm is justified by the higher likelihood of conversion.

A practical recruiter rule is to continue investing when three conditions are present: the candidate has responded, the candidate has passed at least one qualification gate, and the available assessments do not indicate a clear mismatch.

## When Conversion Probability Is Low
Low conversion probability is most visible when there is no response at the start of the funnel. Since only 408 of 601 sourced candidates responded, the non-response group represents the largest and clearest source of low-probability profiles. This means recruiters should avoid overinvesting in repeated outreach when there is no engagement signal after a reasonable sequence of attempts.

Conversion probability is also low when a candidate accumulates weak signals across multiple dimensions, such as slow engagement, failed progression, and poor assessment performance.

Another practical lesson is that some losses are structural rather than recruiter-driven. Rejection reasons such as headcount closure, timing mismatch, salary mismatch, or another accepted offer indicate that not every failure should be interpreted as sourcing quality failure.

## Patterns by Recruiter and Profile
The strongest visible pattern in the exported analysis is channel-related, but profile and context variables also matter. The AI model identified work mode, source channel, department, location, and seniority as relevant features associated with hiring probability.

These coefficients should not be treated as causal proof. They are directional indicators from a simple logistic regression model with an AUC of 0.690, which is useful for prioritization support but not strong enough for autonomous decision-making.

## Applied Use of AI
AI was applied through a simple predictive model designed to estimate which candidate and process characteristics are most associated with hire outcomes. The model used variables such as source channel, department, work mode, seniority, location, years of experience, and response time. Its purpose was to support recruiter prioritization, not to replace recruiter judgment.

This is an appropriate use of AI for a recruiting environment because it improves focus without creating an opaque automated filter. The recruiting team can use the model output to rank pipelines, review high-potential profiles earlier, and identify false positives and false negatives for future calibration.

A good production recommendation would be to keep AI in a human-in-the-loop workflow. Recruiters review the priority suggestions, validate context manually, and track where model suggestions help or fail.

## Recommendations

- Prioritize GitHub, Inbound, and Hunting when building sourcing plans for similar role mixes
- Protect the top of funnel with faster first contact and tighter outreach SLAs
- Use a tiered follow-up logic based on response speed, screening passage, and evaluation consistency
- Reduce late-stage waste by escalating only candidates with both quality signals and process momentum
- Track rejection reasons separately from quality failures
- Use AI scoring as a prioritization layer, with recruiter validation

## Key Decisions Made
Several decisions shaped this solution. Funnel analysis was used as the backbone because it translates directly into recruiting action. Channel analysis was prioritized over more complex segmentation because source strategy is one of the clearest levers available to recruiters. AI was implemented as a lightweight and explainable model rather than a black-box approach, because transparency is more appropriate for a recruiting workflow.

The solution also avoids overclaiming. The data supports practical prioritization insights, but not deterministic rules.

## Conclusion
The analysis shows that the recruiting team can improve outcomes by acting on three levers: source mix, process speed, and prioritization discipline. GitHub, Inbound, and Hunting generated the best hiring outcomes in this dataset, while the biggest funnel loss happened before candidate response and again before offer conversion.

The most useful recruiter behavior is to persist selectively: continue investing in candidates who have responded, passed early qualification, and maintained credible evaluation signals. Use AI-assisted prioritization to focus recruiter effort where conversion probability is higher.
