# prompt-learning-bias
Apply the newly emerging field of prompt engineering to identify and measure social bias in language models

# Custom Dataset
Created custom prompts for detecting bias on BERT, ALBERT and ROBERTA. The dataset follows the same format used in  the CrowS-Pairs dataset (https://github.com/nyu-mll/crows-pairs/blob/master/data/crows_pairs_anonymized.csv).

Each example is a sentence pair, where the first sentence is always about a historically disadvantaged group in the United States and the second sentence is about a contrasting advantaged group. The first sentence can _demonstrate_ or _violate_ a stereotype. The other sentence is a minimal edit of the first sentence: The only words that change between them are those that identify the group. Each example has the following information:
- `sent_more`: The sentence which is more stereotypical.
- `sent_less`: The sentence which is less stereotypical.
- `stereo_antistereo`: The stereotypical direction of the pair. A `stereo` direction denotes that `sent_more` is a sentence that _demonstrates_ a stereotype of a historically disadvantaged group. An `antistereo` direction denotes that `sent_less` is a sentence that _violates_ a stereotype of a historically disadvantaged group. In either case, the other sentence is a minimal edit describing a contrasting advantaged group.
- `bias_type`: The type of biases present in the example.
- `annotations`: The annotations of bias types from crowdworkers.
- `anon_writer`: The _anonymized_ id of the writer.
- `anon_annotators`: The _anonymized_ ids of the annotators.

# Evaluation Metric
For the evaluation metric with use use pseudo-log-likehood MLM scoring. Original source code: https://github.com/nyu-mll/crows-pairs/blob/master/metric.py

# Next Steps
1. Expand custom dataset to 100 samples
2. Re-evaluate MLM scoring metric in all of them
3. Expand it the metric to Auto-Regressive models: GPT-2 => We'll need to modify the original code


# References
https://github.com/nyu-mll/crows-pairs/tree/master