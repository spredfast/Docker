# RESPONSIBILITIES

This service receives proxied traffic from the jwt-proxy service and serves the content on https://status.spredfast.com.

There are plans in the works to migrate it out of k8s and into google cloud to be separate from our other infrastructure.

# DEPENDENCIES

The shared postgres server in exint.

# DEPENDENTS

None. 

# LOCATION

```$ kubectl -n prod get pods -l app=cachet
NAME                     READY     STATUS    RESTARTS   AGE
cachet-626553832-ll2kl   1/1       Running   0          9d
```
It's a singleton because it can't handle auth sessions with 2 web nodes. 

# METRICS

None.

# SMOKETESTS

Does https://status.spredfast.com/ load?

# CONTACT INFO

Outages should be considered P2, not P1, unless someone with more authority contradicts that, though support will act as if it is P0.

nbellamy downloaded the off-the-shelf cachet container and clumsily shoved it into k8s, slack him with questions.