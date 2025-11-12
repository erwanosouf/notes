# Moderne/OpenRewrite Training

## Introduction

### OpenRewrite 

OSS Core : meant for single repository usage
LST + Recipes

### Moderne

Enterprise platform : meant for multi-repository usage
Deploy code changes at scale.

## Key Concepts

### LST

Lossless Semantic Tree stores code structure and formatting.

### Recipes

Reusable code transformations.

Recipes are composable.

### Visitor Pattern

Traverse and modify the LST.

## Recipes

### Declarative Recipes

Compose building blocks in YAML files.
Simple

### Refaster-style

Annotate Before and After states to define transformations.
Limited applicability.

### Imperative Recipes

Use Java Visitor pattern to define transformations.

More complex

## Note on AI Recipes

AI can assist in generating recipes, but human review is essential to ensure correctness and safety.

Recommendation : use AI to suggest recipes and then use Recipes to make changes

## Resources

Concepts :
- [Recipes](https://docs.openrewrite.org/concepts-and-explanations/recipes)
- [LST](https://docs.openrewrite.org/concepts-and-explanations/lossless-semantic-trees)
- [LST : Examples](https://docs.openrewrite.org/concepts-and-explanations/lst-examples)
- [Visitor](https://docs.openrewrite.org/concepts-and-explanations/visitors)

Recipes :
- [Moderne-specific recipes](https://docs.openrewrite.org/reference/moderne-recipes)
- [Common static analysis issue remediation](https://docs.openrewrite.org/running-recipes/popular-recipe-guides/common-static-analysis-issue-remediation)
- [AssertJ Best Practices](https://docs.openrewrite.org/recipes/java/testing/assertj/assertj-best-practices)
- [SpringBoot 3.5 CE](https://docs.openrewrite.org/recipes/java/spring/boot3/upgradespringboot_3_5-community-edition)

Hands-on Learning :
- [Fundamentals](https://docs.moderne.io/hands-on-learning/fundamentals)
- [Advanced](https://docs.moderne.io/hands-on-learning/advanced)

Advanced Program Analysis :
- [Control Flow](https://docs.moderne.io/openrewrite-advanced-program-analysis/control-flow)
- [Data Flow](https://docs.moderne.io/openrewrite-advanced-program-analysis/data-flow)

- [GitHub Copilot App Modernization (uses OpenRewrite)](https://learn.microsoft.com/en-us/java/upgrade/quickstart-upgrade)
- [Stop breaking CI—annotate PRs with OpenRewrite recipe fixes as your quality gate](https://www.moderne.ai/blog/stop-breaking-ci-annotate-prs-with-openrewrite-recipe-fixes-as-quality-gate)
