# Blueprintr

## Problem

1.  Lack of transparency and lineage across the product and software development life cycle.

## Objective

-   **Reduce time to assignment:** Students should be able to get to an assignment from setup in  ≤ 2 minutes. (What is the average time to complete interest selection?  This will give us a clearer goal to hit.)
-   **Provide relevant personalization: Students should be satisfied with their assignment personalization.  This means a.) they can find and select interests they like, or b.) they like the interests selected for them.**

## Context

User Stories:

1.  As a student, I want to find the people and characters that matter to me so that I can have a personalized and engaging experience on NoRedInk.
2.  As a teacher, I want to understand why and how my students are selecting interests, so I can plan my class around that.
3.  As a teacher, I want my students to select interests quickly so that we can move on to the actual assignments.

## Use Cases

Students want:

-   **(Priority 1)** Assignments and stories that match their interests

Teachers want:

-   **(Priority 2)** To focus on assignments
-   **(Low Priority)** To plan classes around interests

Feedback tickets currently support user stories #1 and #2, so we’ll focus on those use cases.  We assume the support tickets are a good representative sample of the user base. Use cases are prioritized to provide team with a focused direction.

## Feature Brainstorm

For the feature brainstorm, we list all ideas before paring them down.  Brainstorming should be completed as a team if resources and time permit.  Options can be ranked using a team scorecard (e.g. super score of impact, resources, time, and intangibles).  Below are some suggested features with feedback:

1.  **Search Bar** – Searching for interests can reduce interest selection time, but it requires students to know what they want.  May not reach minimum interests number.
2.  **Display Similar Interests After Selection** – Similar interests can decrease setup time, but does not solve for finding interests.
3.  **New Top of Page Explanation** – This solution assumes students are taking a long time selecting interest because they do not understand the process.
4.  **Teachers Experience Selection Flow When Viewing as Student** – This improves understanding, but the onus is on teachers to reduce setup time.
5.  **Selection Timer** – This can give students and teachers a time context, but can create a stressful experience.  Students have to race against the clock.
6.  **Like System** – Students skip selection and go straight to assignments.  They can “like” or “dislike” topics at the end of each assignment/question.  These act as interest selections. Students may not want to rank topics after an assignment.

## Proposal

We should create the Like System because it addresses priority 2 by reducing time to assignment to zero.  Executed properly, students will receive the same quality of personalization (priority 1). Rather than front loading the interest selection, the system spreads selection across multiple assignments.  Psychologically, this feels seamless for both users (see [Paradox of Choice User Study](https://hbr.org/2006/06/more-isnt-always-better)) with minimal impact on their sense of control/choice.  

Additionally, the Like System can be leveraged for other explicit feedback: which types of questions do students find helpful?, do they like a new feature?, etc.  A strong feedback system strengthens our two values of “putting teachers and students first” and “relentlessly improving”.

**Proposed Backlog**

The backlog is prioritized based on what needs to be built to reach minimum viability. Must-Haves are critical for launch, High-Wants provide good value but aren’t necessary, and Nice-To-Haves are conveniences.

1.  **(Must-Have)** After answering a grammar question about *|topic|*, student must answer a *|topic|* question: Would you like more sentences about *|topic|*?
2.  **(Must-Have)** This process repeats until student has answered 40 *|topic|* questions and met minimum interest number.
3.  **(Must-Have)** Not answering *|topic|* questions will send a prompt to the student to answer. “Answering this question is required.  It makes sure we give you topics that you enjoy.” (Answers case of not responding)
4.  **(High-Want)** *|topic|* algorithm learns students interests and can present *|topics|* students are more likely to enjoy based on previous selections.
5.  **(Nice-To-Have)** During this assessment phase, *|topic|* is selected randomly from a pool of interests that a majority of students in that demographic (age, grade, etc.) like.
6.  **(Nice-To-Have)** Traditional interest selection page will be accessible as an option in preferences
7.  **(Nice-To-Have)** Interests can be viewed by students in their preference page.
8.  **(Nice-To-Have)** Teachers have a view on their dashboard with most liked student topics.
9.  **(Nice-To-Have)** Feature flag to toggle new system for specific users.

We are assuming 40 *|topic|* questions is enough to reach the minimum interest number.  Ideally, we’d speak with data team to determine # of questions so that 99% of students reach the minimum interest number.  What happens in the corner case where a student doesn’t like any *|topic|* after 40+ questions? We can send a follow up email to speak with the student directly and perhaps discover missing interests or user stories.

## Prototype

The Like System should be prototyped on Proto.io to reduce development and market risks. We’ll run it by our engineers first for a feasibility test (Can this be built? How? Can it be built in timeframe?).  This will allow us to refine our spec. Next, we can run a usability test with UX and, if possible, students (Can they figure out how to use it? Are there any missing requirements?). The purpose is to discover and fix issues before entering an expensive development phase.  

## Test

Students and teachers don’t want to waste class time on a nonfunctional feature.  When the feature is built, we’ll test internally in the dev environment first and re-evaluate.  Then, we should ask for opt-ins to try the new system. This sets expectations with users, so if issues occur, they will be more accepting.  If we can reach 9601 students with opt-ins, our results will have 95% confidence with 1% margin of error.

We can start with 10% of opt-ins on launch day and gradually ramp up to 100% in 4 days. Gradual ramp up allows us to control issues (e.g. stop full deployment until discovered bugs are fixed).  More importantly, releasing only to opt-ins means we can test against a control group (traditional interest selection page users).

## Metrics

The Like System has, effectively, a Time to Assignment of zero, making comparison on this metric a bit of a strawman.  I’d say our northstar metrics should express implicitly or explicitly student satisfaction with personalization and teacher satisfaction with setup.  Comparing two groups with different user numbers means that we should focus on percentages and rates rather than raw numbers.

-   **Weekly Active Users/Total Users:** This retention type data allows us to understand implicitly whether the personalization process is satisfactory. Equal or higher percentage in the opt-in group compared with the control group indicates success.
-   **Feedback Ticket % (Personalization Process):** A statistically higher percentage of negative feedback for the personalization process  in the opt-in group suggests we’ve failed to deliver with our new system.
-   **Interest Completion Rate:** Are enough students reaching the Minimum Interest Number for personalization?  Are we comfortable w/ the trade off (speed vs. completion rate)?

## Next Steps

-   **If we see low student satisfaction (complaints and low retention)**, we’d do a biopsy to determine causes. For example, do students feel like they lack control over interests now? If so, will interest options in the preferences page change that?
-   **If the test succeeds, we can roll out to our entire base with new onboarding and support documents.  We can look at how it can utilized for other feedback functions.**

## Timeline

-   Day 1 – First Draft and Team Feedback
-   Day 2 – Second Draft
-   Day 3 – Prototype
-   Day 4 – Feasibility Test and Adjustments
-   Day 5 – Usability Test and Adjustments
-   Day 6 – Spec Review: Enough info for team to build? What’s missing?
-   Day 7 – Design
-   Day 8 – Development
-   Day 12 – Test w/ Team on Dev Environment and Re-evaluate
-   Day 13 – Send Opt-in Email
-   Day 16 – Launch to Opt-ins (QA and I on deck to respond to issues)
-   Day 23 – Sync (Weekly) for Issues and New Tasks
-   Day 37 – Final Sync (Review Stats, Continue or Next Test?)

## Summary

We’ll improve interest selection by removing the traditional interest page and allowing students to like topics at the end of each question or assignment.  Our users are sensitive to disruptions, so we will prototype and test first before rolling out to a opt-in group. We’ll make adjustments during the project. At the end, we’ll analyze the results and decide whether to continue to next steps or try other solutions.  The total time for the project is 6 weeks.

## Additional Thoughts

With more time, I would include wireframes with the spec because it makes understanding the feature improvements much easier.  Engineers, UX, QA, and Data are brought in early to optimize for success. They can unveil conditions or requirements that may have been overlooked. We’ve assumed that the Like System is relatively easy to implement, but there may be underlying systems that make it complicated.  Engineering would be able to quickly point that out in a feasibility test before development occurs. The backlog items can also be linked with objectives to better explain their impact on the value proposition.

There are a few caveats as well.  For example, the students could be satisfied with the Like System, but teachers may dislike the extra time students take to answer their assignments. Is this worthwhile tradeoff to make? We’d probably need to do expected value calculations to determine that.  A/B testing may be difficult if teachers onboarding students is not a frequent activity. We’d have to plan around specific onboarding windows (likely seasonal).

Finally, I made a tradeoff to focus on a system that is probably harder to build but leveraged for all types of feedback.  This kind of data has high upside in a SaaS business such as NoRedInk. Other features may have more proven results or easier implementation.  They would be great choices if we need to hit specific metrics in a certain timeframe.