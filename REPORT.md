# Assignment 1 Report

*Delete this italic guidance as you fill in each section. You'll be asked to
defend any of this without your code in front of you — write only what you
can actually explain.*

- **Name**:Marco Celati
- **Student ID**:19219
- **Email**:mcelati.ieu2022@student.ie.edu
- **Group**:BBADBA 5A

## Dataset

This dataset called "Default of credit card clients" is about credit card clients from a bank in Taiwan from April to September 2005 and looks at whether they defaulted on their October 2005 payment. I obtained it from the UC Irvine ML repo online. I also converted it from a .xls to a .csv. There are 30,000 rows and 25 columns, of which 1 is the ID, 23 are features, and 1 is the target. The reason I chose this dataset is because I'm highly interested in financial markets and especially the most recent credit issues with US bonds recently having signficantly increased. Hence, these recent times gave me the specific interest in a dataset focused on credit.

## Business / real-life framing


The hypothetical scenario served is that within a bank, the team who's responsible for retrieving the money from the loans at the end of September 2005 will look at the model's scoring of each client. Flagged clients would get a reminder call before the October due date, and if they say they can't pay, they could be offered a payment plan such that the bank could ideally still make back the money that they were owed, albeit after more time.
The target is whether the client defaulted on their October 2005 payment. Regarding the time-based split, each of our clients had the same result month of October 2005, so since there's only one result month, there's nothing to split. Instead, we used a stratified random split which will have the 22% defaulters in both the train and test.
The metric that should drive my decision threshold is total expected cost, and below are the costs of each outcome:
Client is not flagged, pays:NT$0
Client is flagged, pays:NT$50
Client is flagged, defaults:NT$50+80% of the loss
Client is not flagged, defaults:100% of the loss
Flagging and calling a client costs NT$50 which should represent the time being invested into the call. Whereas when they're flagged and default, we assume that 20% of those people who would've otherwise defaulted are now able to repay the loan following the call which served as a reminder, or due to the payment plan offered to them if they weren't able to pay.
The reason a different metric such as Accuracy shouldn't be used is because accuracy treats every mistake as equally bad, however, in our case a wasted call is nowhere as bad as not flagging a defaulter, one mistake costs us much more than the other.


## Data preparation & feature engineering

*What you engineered and why, and any data-quality decisions you made along
the way — e.g. "segment X had defective data, so I excluded it and used a
population-average default for scope Y at inference time; the impact of
that choice is Z."*

## Modeling: three implementations, one model

*Which model (linear or logistic regression) and why. A results table
comparing scikit-learn, the manual PyTorch loop, and the standard
torch.nn.Module/torch.optim workflow, on the same test set, against the
naive baseline. Do the three agree? If not, why not?*

## Limitations & next steps

*Real limitations you found, and concretely how you'd address each one with
more time or data — not generic hedging.*

## Generative AI use disclosure

*Per the syllabus AI Policy: what you used and how, or "no AI content used."*
