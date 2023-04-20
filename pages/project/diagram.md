---

# Diagrams

CI Diagrams

<div class="grid grid-cols-1 gap-10 pt-4 -mb-6 text-center">


```mermaid {theme: 'neutral', scale: 0.8}
flowchart LR
    A[SCM git] -->|push| B(Actions CI)
    B --> C[SonarQube]
    C --> |Pass| D[Deploy]
    C --> |Fail or need fix| A
```

</div>