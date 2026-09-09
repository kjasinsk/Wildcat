# Prompting Strategy Comparison

**Question tested:** "What are the most important metrics for measuring credit risk in a consumer loan portfolio?"

Each response below is capped at the first 150 words.

---

## Strategy 1 — Zero-Shot

**Technique:** Ask the question exactly as written, with no additional context.

**Response (150 words):**

The metrics that matter most for a consumer loan portfolio generally fall into a few groups, each answering a different question.

For borrower-level risk at origination, the core three are credit score (a summary of past repayment behavior), debt-to-income ratio (how much of a borrower's income is already committed to debt, which measures capacity to take on more), and loan-to-value ratio for secured loans like auto or home-related lending (how much cushion exists if the lender has to repossess and sell the collateral). Income itself matters mostly as a scale check rather than a risk signal on its own.

For the portfolio as a whole, the standard health metrics are the default rate (share of loans that have gone to loss), the delinquency rate broken into stages like 30/60/90 days past due (an early-warning view of loans heading toward trouble), and the roll rate or migration rate — what share …

---

## Strategy 2 — Role-Assigned (Role + Audience)

**Technique:** "You are a senior credit risk analyst at JP Morgan presenting to the US Treasury on credit metrics in your excel file. Answer this question for them: 'What are the most important metrics for measuring credit risk in a consumer loan portfolio?'"

**Response (150 words):**

Credit Risk Metrics for a Consumer Loan Portfolio

Thank you for the opportunity to walk through this. When we evaluate credit risk in a consumer loan portfolio, we look at it in layers — borrower-level underwriting metrics, portfolio-level performance metrics, loss-severity metrics, and forward-looking indicators. No single number tells the full story, so we rely on this framework together.

At the borrower level, the three metrics that carry the most underwriting weight are credit score, debt-to-income ratio, and loan-to-value ratio for secured products. Credit score is our best single predictor of repayment behavior because it reflects a track record over time. DTI measures a borrower's current capacity to absorb additional debt, independent of history. LTV, where collateral is involved, tells us how much of our exposure is actually protected if a loan goes bad. We treat these as complementary rather than interchangeable — a strong score doesn't offset an unsustainable …

---

## Strategy 3 — Few-Shot

**Technique:**

> Here's the format I want you to use:
>
> Point: [a short label for the idea]
> Explanation: [one to two sentences explaining it]
> Why it matters: [one sentence on the practical implication]
>
> (That's just the format — not a real answer.)
>
> Now, using that exact format, answer: "What are the most important metrics for measuring credit risk in a consumer loan portfolio?"

**Response (150 words):**

**Point:** Credit Score
**Explanation:** A summary of a borrower's historical repayment behavior, derived from prior credit accounts, payment timeliness, and credit utilization.
**Why it matters:** It's the single strongest predictor of default risk at the point of underwriting.

**Point:** Debt-to-Income Ratio (DTI)
**Explanation:** The share of a borrower's income already committed to debt payments before any new loan is added.
**Why it matters:** It measures current capacity to take on more debt, independent of credit history, so it catches borrowers who are stretched thin even with a good score.

**Point:** Delinquency Rate (by aging bucket: 30/60/90 days past due)
**Explanation:** The share of loans currently behind on payments, broken out by how far behind they are.
**Why it matters:** It's a leading indicator — it shows where the default rate is likely headed before that loss actually materializes.

**Point:** Roll Rate / Migration Rate
**Explanation:** The pace at which loans …

---

## Fact-Check

**1. The exact claim Claude made:**

> "...the move between them usually happens after a sustained period of nonpayment (commonly around 90 days)..."

(From Claude's explanation of when a loan moves from delinquency to default.)

**2. Source used:**

Federal Reserve / FDIC — *Uniform Retail Credit Classification and Account Management Policy* (Federal Reserve Supervisory Letter SR 00-8; FDIC FIL-40-2000)
URL: https://www.fdic.gov/news/financial-institution-letters/2000/fil0040a.html

**3. What the source says:**

The policy sets two different charge-off thresholds by loan type, not one universal number: closed-end retail loans (installment loans — e.g., auto, personal, home improvement, education, which is most of Wildcat's book) that become 120 cumulative days past due should be classified Loss and charged off. Open-end retail loans (revolving credit, e.g., credit cards) are charged off at 180 cumulative days past due.

**4. Do they agree, and what does this say about reliability:**

They don't fully agree. Claude's "commonly around 90 days" is not the number banking regulators actually use for charge-off — the real thresholds are 120 days (closed-end) and 180 days (open-end). The 90-day figure isn't fabricated; it does appear in real sources (e.g., the CFPB tracks "90 or more days delinquent" as its benchmark for serious mortgage delinquency), but it describes a delinquency-severity label, not the formal default/charge-off trigger. Claude conflated two related but distinct thresholds. The takeaway: numeric thresholds Claude states from general knowledge (days-past-due rules, regulatory percentages, specific cutoffs) should be treated as plausible-but-unverified until checked against a primary source — Claude tends to get the general shape of a rule right (there is a days-past-due threshold, and it does distinguish loan types in spirit) but can round toward a more commonly repeated number rather than the exact regulatory figure.
