# TeamLease: team-lease

This repo holds the product and its records: the order, the plan, the jobs, and every run's record. The
factory that builds it (its crew, prompts and checkpoints) is not here: it is the engine named in
`.factory-engine`, installed on the machines that run the crew and pulled by CI.

    ./bin/factory doctor       what this machine needs
    ./bin/factory jobs         every job and its next step
    ./bin/factory run --cloud developer T-004   a crew run on GitHub Actions (.github/workflows/factory-run.yml)
