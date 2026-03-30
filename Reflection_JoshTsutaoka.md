# Student A Reflection
## BSAN 6200: Text Mining & Social Media Analytics
## Assignment 3: Topic Modeling

## What I Learned

This assignment was the first time I worked with unsupervised NLP and the difference
from the supervised assignments was immediately obvious. There is no right answer to
check against. You have to look at what the model produces and decide for yourself
whether it makes sense. The technical side came together through iteration. Early runs
had coherence scores below 0.5 for two of the three groups. Going back through the
topic word outputs I could see words like "end", "guy", "man", and "world" showing up
across multiple topics without actually meaning anything. Removing those and tightening
the min_df threshold pushed the scores up. That back and forth between looking at
outputs and adjusting inputs is something I did not expect to spend as much time on
as I did.

The k tuning sweep was also interesting because the data did not agree with the
assignment. k=5 and k=8 outperformed k=10 on coherence across all three groups. We
kept k=10 because it was required but documenting that tradeoff honestly felt like
the right call rather than just pretending the sweep did not happen.

## Topic Interpretation

Interpreting the topics without AI was harder than I expected but also more satisfying.
Some topics were straightforward. Ledger's Joker in Group 2 and the Spider-Man topic
in Group 1 had clear enough word signals that the name came quickly. Others took more
work. The Infinity Holes topic in Group 1 had words pointing in a few different
directions at once and I had to read actual reviews to understand what was driving
that cluster. It turned out to be reviewers frustrated with the time travel logic
which is not something you could get from the word list alone.

Group 3 was the most interesting to interpret. Thor Ragnarok, John Wick, and Morbius
have almost nothing in common but LDA still found coherent themes. It also had the
highest coherence score of the three groups which surprised me at first but makes
sense when you think about it. The contrast between those films probably helped the
model find cleaner separations than the more stylistically similar MCU films in Group 1.


## Challenges

The Dark Knight data issue took longer than expected to diagnose. About 2,197 rows
were unrecoverable no matter what encoding or parser settings I tried. Eventually I
accepted it as a source-level problem and documented it as a data limitation. That was
a better outcome than pretending the rows were not missing.

Getting coherence above 0.5 consistently also took more rounds of stopword refinement
than I anticipated. You have to actually look at what the model is outputting and
reason about why certain words keep appearing before you know what to remove. There is
no shortcut for that.

## Collaboration

My partner handled NMF while I owned the LDA pipeline and preprocessing. The shared
decisions were dataset selection, group definitions, number of topics, and the overall
structure. It worked well because the tasks were connected. My preprocessing output
fed into my partner's NMF input so we had to stay coordinated on the cleaning
settings.


