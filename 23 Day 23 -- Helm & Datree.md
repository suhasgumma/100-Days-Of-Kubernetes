## Day 23 -- Helm & Datree
### Fundamentals Of Helm

#### What is Helm?

Package Manager for Kubernetes. Primary Feature is packaging YAML files & distributing them in Public & Private repositories. Second feature is Templating engine.

#### What are Helm Charts?

Bundle of YAML files.

#### Helm Chart Structure
```
chartName/
  chart.yaml    //chart's metadata
  values.yaml   // Substitutes in template files
  charts/       // Chart Dependencies
  templates/
```

### Introduction to Datree

#### Problem Datree is Solving --> Preventing Kubernetes Misconfigurations from reaching Production. 

#### Does that through a series of checks
✨ YAML Validation.

✨ Kubernetes Schema Validation 

✨ Policy Check (Check the policies selected beforehand from available polocies. Currently there are 60 polocies)

### Datree policies
<img src="Images For Readme/Datree Policies.png" height = 300 width = 500>

### Kubernetes Schema Validation Fail
<img src="Images For Readme/Kubernetes Schema Validation Fail.png" height = 300 width = 500>

### Policy Check Fail
<img src="Images For Readme/Policy Check Fail.png" height = 300 width = 500>