# Workload Identity Federation with Github Actions: Small Org Usecase

## Architecture

``` mermaid
C4Container
  Person(user, "Developer", "A developer who triggers GitHub Actions")

  System_Boundary(gitRepos, "Git Repositories") {
    Container(platRepo, "Platform Repository", "Git Repo", "Contains platform infrastructure")
    Container(consumerRepo, "Consumer Repository", "Git Repo", "Contains consumer infrastructure")
  }

  System_Boundary(gcp, "Google Cloud Platform") {
    System_Boundary(wlifProj, "WLIF/Platform Project") {
      Container(wlifPool, "WLIF Pool")
      Container(wlifProvider, "WLIF Provider")
    }
    System_Boundary(consumerProj, "Consumer Project") {
      Container(consumerRes, "Consumer Resources")
    }
  }

  Rel(platRepo, wlifPool, "creates")
  Rel(platRepo, wlifProvider, "creates")
  Rel(consumerRepo, wlifProvider, "uses")
  Rel(consumerRepo, consumerRes, "creates")
  Rel(user, platRepo, "changes")
  Rel(user, consumerRepo, "changes")
  
```

WLIF project is the first thing you create. This doesnt have to be seperate projects
