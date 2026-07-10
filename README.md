# Selective Regeneration Benchmark

Benchmark accompanying the paper:

> **Don't Regenerate What Hasn't Changed: Selective Regeneration for Token-Efficient LLM-Driven Software Evolution**

This repository contains the benchmark used to evaluate a dependency-aware selective regeneration pipeline for requirement-driven software evolution with Large Language Models (LLMs).

---

## Overview

Current LLM-assisted software evolution typically regenerates large portions of a project whenever requirements change. This benchmark evaluates an alternative strategy:

**Selective Regeneration**

Instead of regenerating the complete context, only artefacts affected by a requirement change are regenerated.

The benchmark compares two pipelines:

- Agent-based retrieval baseline
- Dependency-aware Selective Regeneration pipeline

using identical models and prompts.

---

## Pipeline

Natural Language Requirement

↓

YAML DSL

↓

SHA-256 Change Detection

↓

Dependency Graph

↓

JSON Intermediate Representation

↓

BDD (Gherkin)

↓

TDD (pytest)

↓

Source Code

---

## Benchmark

The benchmark uses a realistic Hospital Management System consisting of

- 12 entities
- approximately 70 source files
- 8 architectural layers
- 65+ REST endpoints
- 90 tests

Ten sequential requirement changes are applied to simulate software evolution.

---

## Metrics

The benchmark reports

- Total input/output tokens
- Token reduction
- Number of regenerated files
- Blast radius
- Context reconstruction ratio
- Execution time

The paper focuses on token consumption and regeneration scope.

---

## Model

Experiments were conducted using

- Qwen2.5-Coder-7B-Instruct

through the HuggingFace Inference API.

The benchmark is model-agnostic and can be executed with other LLMs.

---

## Repository Structure
