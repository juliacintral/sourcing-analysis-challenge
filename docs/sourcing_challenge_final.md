# Technical Challenge — Sourcing Analysis with AI

## Overview
This project analyzes a fictional sourcing and recruitment dataset to identify which sourcing strategies convert best, what candidate signals indicate a higher chance of advancing, when it is worth persisting with a candidate, and when conversion probability is low. The analysis combines funnel diagnostics, channel-level comparisons, practical recruiter recommendations, and a predictive AI model used to support prioritization decisions.

The dataset contains 601 sourced candidates, with progression tracked across response, screening, interview, assessment, offer, and hire stages. The overall goal is not only to describe performance, but to turn the data into actions recruiters can apply in day-to-day pipeline management.

## Approach
The analysis was structured in four layers. First, a funnel analysis measured drop-off between stages to identify the largest leaks in the process. Second, sourcing channels were compared on response, screening, interview, offer, and hire rates. Third, behavioral and process signals such as response time, assessment scores, and stage progression were interpreted to determine where persistence is worthwhile. Fourth, a simple machine learning model was used to estimate which variables were most associated with hiring outcomes.

This approach was chosen because it balances business relevance and technical clarity. A recruiter or talent leader needs more than a descriptive dashboard — they need to know where to invest effort, where to stop spending time, and how to use AI responsibly to support prioritization.

## Funnel Analysis
The funnel starts with 601 sourced candidates, of whom 408 responded, 308 passed screening, 234 advanced through the first interview, 201 completed an assessment, 62 received an offer, and 49 were ultimately hired. This shows that the process loses talent steadily at every stage, with especially significant losses between sourcing and response, and again between assessment completion and offer.

These numbers suggest two operational questions matter most. The first is whether recruiters are reaching the right people and engaging them quickly enough to secure a response. The second is whether the team is being selective early enough so that later-stage effort is concentrated on candidates with a stronger probability of offer and hire.

## Channel Performance
Channel analysis shows meaningful differences in conversion quality. GitHub had the highest observed hire rate at 11.0%, followed by Inbound at 10.1% and Hunting at 9.3%. Talent Pool and LinkedIn produced hire rates of 8.8% and 8.6% respectively, while Event and Referral had the weakest final conversion rates in this dataset, at 4.9% and 4.7%.

Inbound and Talent Pool also showed relatively strong response rates, at 79.7% and 75.0%, while LinkedIn and Hunting were lower at 63.0% and 64.0%. GitHub stood out as a balanced channel because it combined solid response levels with the strongest final hiring outcome.

One important nuance is that Referral had the highest average technical score at 80.4, but did not translate that quality signal into strong hiring conversion. This suggests that technical strength alone is not sufficient — process speed, fit alignment, and downstream decision quality also matter.

## Advancement Signals
The dataset suggests that early responsiveness is a meaningful signal. Channels with faster average response time, such as Talent Pool and Inbound, tended to support stronger early-stage conversion. In practice, candidates who engage quickly are easier to move through the process, easier to schedule, and less likely to stall the funnel.

Assessment performance also matters, but in combination with process signals. The evidence indicates that candidates with stronger technical, behavioral, and manager scores are more likely to remain viable deeper in the funnel — yet high scores alone do not guarantee hire if timing, motivation, or business constraints interfere.

Recruiters should evaluate advancement using a combination of variables: source channel, response speed, screening outcome quality, and consistency across evaluation stages.

## When Persistence Is Worth It
Persistence tends to be worthwhile when a candidate has already signaled intent and capability. Candidates who responded, cleared screening, and maintained acceptable evaluation scores should remain in active follow-up even when there are short delays caused by scheduling, competing processes, or internal timing.

This is especially true for candidates from higher-performing channels such as GitHub, Inbound, and Hunting. When those profiles also show fast response behavior and steady progression, the incremental effort to keep them warm is justified by the higher likelihood of conversion.

A practical rule: continue investing when three conditions are present — the candidate has responded, the candidate has passed at least one qualification gate, and available assessments do not indicate a clear mismatch.

## When Conversion Probability Is Low
Low conversion probability is most visible when there is no response at the top of the funnel. Since only 408 of 601 sourced candidates responded, the non-response group represents the largest and clearest source of low-probability profiles. Recruiters should avoid overinvesting in repeated outreach when there is no engagement signal after a reasonable sequence of attempts.

Conversion probability is also low when a candidate accumulates weak signals across multiple dimensions — slow engagement, failed progression gates, and poor assessment performance together.

Another key lesson: some losses are structural rather than recruiter-driven. Rejection reasons such as headcount closure, timing mismatch, salary mismatch, or another accepted offer indicate that not every pipeline failure should be interpreted as a sourcing quality failure.

## Patterns by Recruiter and Profile
The strongest visible pattern in the analysis is channel-related, but profile and context variables also matter. The AI model identified work mode, source channel, department, location, and seniority as relevant features associated with hire probability.

These coefficients should not be treated as causal proof. They are directional indicators from a simple logistic regression model with an AUC of 0.690 — useful for prioritization support but not strong enough for autonomous decision-making.

## Applied AI Usage
AI was applied through a predictive model designed to estimate which candidate and process characteristics are most associated with hire outcomes. The model used variables such as source channel, department, work mode, seniority, location, years of experience, and response time. Its purpose is to support recruiter prioritization, not to replace recruiter judgment.

This is an appropriate use of AI for a recruiting environment because it improves focus without creating an opaque automated filter. The team can use model output to rank pipelines, review high-potential profiles earlier, and track false positives and negatives for future calibration.

The recommended production approach is to keep AI in a human-in-the-loop workflow: recruiters review the priority suggestions, validate context manually, and log where model suggestions help or fail. The model is recalibrated monthly with updated outcomes.

## Recommendations

- Prioritize GitHub, Inbound, and Hunting when building sourcing plans for similar role mixes
- Protect the top of funnel with faster first contact and tighter outreach SLAs
- Use tiered follow-up logic based on response speed, screening passage, and evaluation consistency
- Reduce late-stage waste by escalating only candidates with both quality signals and process momentum
- Track rejection reasons separately from quality failures to distinguish operational losses from sourcing failures
- Use AI scoring as a prioritization layer, with recruiter validation at every step

## Key Decisions Made
Several decisions shaped this solution. Funnel analysis was used as the backbone because it translates directly into recruiting action. Channel analysis was prioritized over more complex segmentation because source strategy is one of the clearest levers available to recruiters. AI was implemented as a lightweight and interpretable model rather than a black-box approach, because transparency is more appropriate for a recruiting workflow.

The solution also avoids overclaiming. The data supports practical prioritization insights, but not deterministic rules.

## Conclusion
The analysis shows that the recruiting team can improve outcomes by acting on three levers: source mix, process speed, and prioritization discipline. GitHub, Inbound, and Hunting generated the best hiring outcomes in this dataset, while the biggest funnel loss happened before candidate response and again before offer conversion.

The most effective recruiter behavior is to persist selectively — continue investing in candidates who have responded, passed early qualification, and maintained credible evaluation signals. Use AI-assisted prioritization to concentrate effort where conversion probability is highest.

---
*Technical Challenge — People Analytics & Sourcing with AI*
