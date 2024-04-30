# upstream

This repo demonstrates triggering a pipeline on [a downstream repository](https://github.com/benkn/e2e-testing).

The setup is to [create a Github access token](https://github.com/peter-evans/repository-dispatch?tab=readme-ov-file#token) with specific permissions and add it as a repository secret, in this pipeline's case `E2E_TRIGGER`.

The [trigger-PR-e2es job](https://github.com/benkn/upstream/blob/main/.github/workflows/pipeline.yml#L45) kicks the downstream with variables and [trigger-main-e2es job](https://github.com/benkn/upstream/blob/main/.github/workflows/pipeline.yml#L57) kicks the downstream for every commit to main. The jobs utilize [peter-evans/repository-dispatch](https://github.com/peter-evans/repository-dispatch) jobs to handle the behavior.
