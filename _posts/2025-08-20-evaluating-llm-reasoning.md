---
layout: post
title: A Practical Checklist for Evaluating LLM Reasoning
date: 2025-08-20 09:00:00+0800
description: lessons we learned from benchmarking reasoning abilities of large language models
tags: [evaluation, reasoning, llm]
categories: tutorials
---

Evaluating reasoning in large language models is trickier than it looks. Here is a checklist we have found useful in our own projects.

## 1. Report more than accuracy

Pass@1 alone hides a lot. Pair it with pass@k, self-consistency over multiple samples, and variance across seeds.

## 2. Watch for data contamination

If the benchmark is public, assume it is in the training data. Prefer held-out or newly constructed test sets, and report perplexity-based contamination checks where possible.

## 3. Separate reasoning from retrieval

A model that answers correctly may be reciting, not reasoning. Include adversarial variants — same question, perturbed numbers or entities — to test whether the reasoning chain actually transfers.

## 4. Check the chain, not just the answer

Final-answer agreement between chain-of-thought and direct answering can reveal when the rationale is post-hoc. Report both.

_This is placeholder content — replace it with a real post._
