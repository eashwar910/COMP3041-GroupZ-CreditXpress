## Issue B: The app requests location twice before sign-up and a second denial triggers permanent “don't ask again”

### Violated Code of Ethics

**1.06 Be fair and avoid deception in all statements, particularly public ones, concerning software or related documents, methods and tools.**

Application: The second request is presented to the user as an ordinary permission prompt, but the engineer tied it to leaving the login page, an action unrelated to location or notifications. The prompt's placement implies a relevance to signing in that does not exist. A user who backs out has shown less interest in the service, yet is asked again, and on Android 11+ that second denial is recorded permanently as "don't ask again." Presenting the request as routine while triggering a permanent denial is misleading about what the interaction does.

**3.06 Work to follow professional standards, when available, that are most appropriate for the task at hand, departing from these only when ethically or technically justified.**

Application: Android's own guidance tells developers to "gracefully degrade your app so that the user can continue" after a denial, rather than repeat the request. The app departs from this standard by using every request the operating system allows before the user has signed up or seen any loan terms. No ethical or technical justification is offered for exhausting the system's allowance.

**3.12 Work to develop software and related documents that respect the privacy of those who will be affected by that software.**

Application: Respect for privacy includes respect for a user's answer. When a user denies a permission before having an account or seeing any loan terms, that denial expresses a choice. Re-asking immediately, on an unrelated trigger, and consuming the final allowed request to make the refusal permanent does not respect that choice; it overrides it.

**3.13 Be careful to use only accurate data derived by ethical and lawful means and use it only in ways properly authorized.**

Application: The timing of the request is not properly authorized by the user's current situation. Before sign-up, a legitimate purpose such as screening out overseas applicants has not yet become relevant, and the user has not been given the context to authorize location collection for that purpose. Consuming the permission allowance at this stage uses the user's consent budget for a purpose the user has not yet been told about.

### Ethical Theory

**Deontology**

Deontology is the most suitable theory here because the wrong is a failure to respect the user's decision, independent of the outcome. Kant's categorical imperative requires treating people as ends in themselves. When a user declines a permission, that is a rational choice; re-asking on an unrelated trigger treats the refusal not as a decision to be respected but as an obstacle to be worked around. The universality test confirms this: the engineer would not want all apps to exhaust the permission allowance before a user has any context, because that would make the permission system meaningless.

Deontology also fits because the fair reading concedes the request itself may be legitimate: approximate location for screening overseas applicants and notifications for service updates. The objection is therefore not to what is requested, but to when and how the refusal is handled, which is precisely a question of respect for the user's agency.

### Where the SE Code Is Insufficient

The Code is silent on the specific design question of timing and permission-request budgeting. Clause 3.12 requires respect for privacy but does not tell an engineer what counts as a respectful number of requests or what trigger is appropriate. Clause 3.06 invokes professional standards, but the Android guidance about graceful degradation is a platform recommendation, not a binding clause, and the Code offers no hierarchy for weighing it against management pressure to gather data early.

The decision about when to prompt may also lie with product or growth teams rather than the engineer. Care ethics is the needed supplement: the user at the onboarding stage is in a position of dependence, with no account, no loan terms, and no context, while the company controls the flow and the information. Care ethics asks whether a responsible professional would use an unrelated trigger to consume a vulnerable user's final request and convert a refusal into a permanent denial. The answer is no, and that judgment is what the Code alone cannot supply.



## Issue C: The cost of borrowing is shown as a small daily rate, not an annual rate

### Violated Code of Ethics

**1.03 Approve software only if they have a well-founded belief that it is safe, meets specifications, passes appropriate tests, and does not diminish quality of life, diminish privacy, or harm the environment. The ultimate effect of the work should be to the public good.**

Application: The decision to display only the daily rate of 0.05% while withholding the APR, fees, and total repayment until after the borrower is locked in is a design choice that was approved and deployed. A screen that shows the figure least likely to alarm the borrower and withholds the figure that would enable a realistic assessment of cost diminishes the borrower's quality of life by exposing them to potential financial harm. The ultimate effect is not to the public good but to the company's conversion metrics.

**1.06 Be fair and avoid deception in all statements, particularly public ones, concerning software or related documents, methods and tools.**

Application: The only price shown before sign-up is "Daily rate 0.05%." This figure is technically accurate, but it is presented without the annual percentage rate of approximately 18.25%, which sits at or near Malaysia's 18% cap for unsecured moneylender loans. The daily figure is a public statement about the product, and presenting it as the sole cost indicator while omitting the annual figure is deceptive in effect, even if no individual number is false.

**3.10 Ensure adequate testing, debugging and review of software and related documents on which they work.**

Application: The disclosure flow was not adequately reviewed against the relevant standard for a financial product, namely whether a reasonable borrower can understand the full cost before committing. Apple's App Review Guidelines require personal-loan apps to "clearly and conspicuously disclose all loan terms, including … equivalent maximum Annual Percentage Rate (APR) and payment due date" (Apple, 2026, 3.2.2(ix)). The screen does not meet that standard, which indicates that the review and testing process did not cover the applicable disclosure requirements.

**3.12 Work to develop software and related documents that respect the privacy of those who will be affected by that software.**

Application: In this context, respect for affected persons means respect for their ability to make an informed decision. The terms state that "once you have submitted a loan application, cancellation of the application is not allowed" (Credit Xpress, 2026b), and the full cost appears only in the Moneylending Agreement signed after approval. A design that reveals the full figure only when the borrower can no longer back out does not respect the borrower's autonomy or their interest in controlling decisions that affect them.

**3.13 Be careful to use only accurate data derived by ethical and lawful means, and use it only in ways properly authorized.**

Application: The daily rate is accurate data, but it is used in a way that is not properly authorized by the borrower's interest in informed consent. Using the 0.05% figure as the sole headline while withholding the APR, fees, and stamp duty is a use of accurate data in a manner that the affected person would not authorize if the context were made clear.

### Ethical Theory

**Deontology**

The core wrong is a failure to respect the borrower's rational agency, not a bad outcome. Kant's categorical imperative requires treating people as ends in themselves, not merely as means to the company's revenue. A rational person would want to know the full annual cost before committing. By showing only the daily rate and withholding the APR until after cancellation is barred, the design treats the borrower as a means to conversion. The universality test confirms this: the company would not will that all lenders display only daily rates without disclosure, because such a practice would destroy trust in lending markets. Deontology suits this case because the ethical failure lies in the deliberate omission itself.

**Utilitarianism**

Utilitarianism weighs consequences across affected parties. The company benefits from higher conversion and lower drop-off. Borrowers are harmed by exposure to unaffordable repayments and the inability to cancel once the application is submitted. The aggregate harm to borrowers—financial distress, damaged credit, debt cycles—outweighs the benefit to the company. The design exploits information asymmetry for short-term profit at the expense of long-term trust and welfare. Utilitarianism makes explicit the trade-off the company made and shows the net effect is negative.

**Care Ethics**

The borrower is vulnerable due to financial need and limited understanding of compound rates, and the design exploits this imbalance. Care ethics asks whether a caring, responsible professional would reveal the full cost only when the borrower cannot back out. The answer is no. This theory captures the relational dimension the Code cannot, and it guides engineers whose concerns are ignored: continue advocating for the vulnerable party and document the concerns.
