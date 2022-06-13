# Labels, Selectors and namespaces
These constructs allows us to anitate and organise our applications so that when we have a lot of them, Kubernetes operators still understand whats still going on holistically.

## Labels
Labels are key/value pairs that are attached to objects like pods, services and deployments.
- Labels are for users of kubernetes to identify attributes for objects. 

******Examples******
"release": "stable"
"release": "canary"
"environment": "dev" 
"tier": "frontend"
"tier": "backend"

## Selectors
Label selectors allows you to identify a set of objects.

****Types of Selectors****
1: Equality based
- includes = and !=
- = : two labels or value of labels should be equal
- != : the values of the labels should not be equal
2: Set based 
- IN : A value should be inside a set of defined values. 
- NOTIN : A value should not be inside a set of defined values.
- EXISTS : Determines if a label exists or not.

## Namespaces
Unlike labels and selectors, namespaces allows you to have multiple virtual clusters backed by the same physical cluster .
They also provide scope for names-must be unique in the namespace.
