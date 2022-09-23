# Big Code Project

This repository serves as place for administrative things and a place for generic todos and issues. The main code can be found in the following repositories.

## [Megatron-LM](https://github.com/bigcode-project/Megatron-LM)
This repository contains the Megatron-LM fork used for training the BigCode models.

## [bigcode-analysis](https://github.com/bigcode-project/bigcode-analysis)
The BigCode analysis repository is a place for all kinds of analysis reports.

## [bigcode-evaluation-harness](https://github.com/bigcode-project/bigcode-evaluation-harness)
The BigCode evaluation harness is developed to evaluate language models for code on several benchmarks.

## [bigcode-website](https://github.com/bigcode-project/bigcode-website)
The BigCode website contains the source of the website.

# What has been done and how can you help?

📚 **Dataset**: We’ve collected 120M+ Github repositories and ran a license detector on them. We will soon release a dataset with files from repositories with permissive licenses. We’ve also implemented a [near-deduplication process](https://github.com/bigcode-project/bigcode-analysis/tree/main/data_analysis/near-deduplication) for the dataset.

Besides Github, we would like to add more datasets. You can help by suggesting good data sources in [this github issue](https://github.com/bigcode-project/admin/issues/15) and join the #wg-dataset channel. We also welcome you to join the channel if you are interested in discussions about data governance. 

🕵🏻‍♀️ **Evaluation**: We started working on an [evaluation harness](https://github.com/bigcode-project/bigcode-evaluation-harness) to evaluate code generation models in an easy way on a wide range of tasks.

You can help by discussing the [current set of tasks](https://docs.google.com/spreadsheets/d/1otSgs2-iDp1KTbasEDlFhTHiaKsYbIRvWrgH_TiubFQ/edit?usp=sharing), suggesting missing evaluation tasks, and joining the #wg-evaluation channel. We also created a list of “Good first issues” [here](https://github.com/bigcode-project/bigcode-evaluation-harness/issues?q=is%3Aopen+is%3Aissue+label%3A%22good+first+issue%22).

💪 **Training**: We’ve been training smaller models (350M-1B parameters) on the ServiceNow cluster through a [fork of Megatron-LM](https://github.com/bigcode-project/Megatron-LM). 
- We’ve ported [ALiBi](https://arxiv.org/abs/2108.12409) in order to support longer sequences at inference time
- We’ve implemented [multi-query attention](https://arxiv.org/abs/1911.02150) so as to speed-up incremental decoding
- The goal is to scale to a ~15B parameter model. We will, however, first run several ablation studies on a smaller scale. We will soon release our experiment plan and solicit your feedback!

If you have experience with large-scale transformer training in a multi node setup, please join the #wg-training channel. 

🏎 **Inference**: We’ve implemented multi-query attention in Transformers and Megatron-LM. While [others](https://arxiv.org/abs/1911.02150) have reported significant speed-ups, we’ve only seen modest improvements of ~20%. You can find the benchmarks in this [issue](https://github.com/bigcode-project/transformers/issues/1). If you are interested in investigating how to speed-up inference, please go to the #wg-inference channel. 

