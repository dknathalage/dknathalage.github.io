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
  }

  Rel(platRepo, wlifPool, "creates")
  Rel(platRepo, wlifProvider, "creates")
  
```

WLIF project is the first thing you create. This doesnt have to be seperate projects
