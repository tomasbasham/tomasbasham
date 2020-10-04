```go
package profile

import (
  "net/url"

  github "github.com/github/user"
  linkedin "github.com/linkedin/user"
)

type Tomas struct{}

func (*Tomas) CurrentRole() linkedin.Experience {
  return linkedin.Experience{
    Company:  "StatusCake",
    Position: "Software Developer",
  }
}

func (*Tomas) About() github.Profile {
  return github.Profile{
    Languages:    []string{"Go", "Python", "Ruby", "Rust", "Swift"},
    Tools:        []string{"Docker", "Kubernetes", "Terraform"},
    Architecture: []string{"Microservices", "Event driven", "Heaxagonl"},
    Platforms:    []string{"AWS", "GCP", "iOS"},
  }
}

func (*Tomas) Projects() []github.Project {
  return []github.Project{
    Project{
      Name: "ratelimit",
      URL:  mustParse(url.Parse("https://github.com/tomasbasham/ratelimit")),
    },
    Project{
      Name: "dotfiles",
      URL:  mustParse(url.Parse("https://github.com/tomasbasham/dotfiles")),
    },
  }
}

func (*Tomas) Links() map[string]*url.URL {
  return map[string]*url.URL{
    "Website":  mustParse(url.Parse("https://tomasbasham.dev")),
    "Linkedin": mustParse(url.Parse("https://www.linkedin.com/in/tomasbasham")),
  }
}
```
