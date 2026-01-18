# HCEP - Hack Club Enhancement Proposals

[![Static Badge](https://img.shields.io/badge/Hack_Club_slack-%23hceps-blue?style=flat-square&logo=hackclub)](https://hackclub.enterprise.slack.com/archives/C09ULRQ02KT)

> [!NOTE]
> We're working on the process of submitting and reviewing HCEPs behind the scenes! In the meantime, please feel free to open issues or reach out on Slack if you have any questions.

This is a Git repository containing Hack Club Enhancement Proposals (HCEPs). HCEPs are proposals for significant changes or additions to Hack Club's programs, infrastructure, or community practices.

This setup follows the model of Fediverse Enhancement Proposals (FEPs) and Python Enhancement Proposals (PEPs), among other similar RFC-style pratices
in the wider open-source community.

The HCEP process is a community initiative by Hack Clubbers for Hack Clubbers. While it is not an official Hack Club HQ process yet or intended to replace the `#meta` Slack channel, it exists to facilitate and improve meta discussions about Hack Club itself as both an organization and community space.

## Submitting a HCEP

To create and submit a HCEP:

1. Fork this repository and clone to your computer. Alternative, you can use [`github.dev`](https://github.dev/hackclub-community/HCEP) or [VS Code for the Web](https://vscode.dev/github/hackclub-community/HCEP) to edit files directly in your browser. GitLab users can use [the GitLab Web IDE](tbd) to edit on the GitLab.com mirror of this repository.
2. Think of a title for the FEP you want to submit.
3. Compute the identifier of the HCEP by computing the hash of the title. This can be done with following Unix command:

```shell
$ echo -n "The title of my proposal" | sha256sum | cut -c-4
b3f0
```

## Maintainers

The list of the HCEPs as well as the website version of it and the Slack channel are maintained by HCEP falicators/maintainers listed at [`site/maintainers.md`](./site/maintainers.md).

## License

CC0 1.0 Universal (CC0 1.0) Public Domain Dedication

To the extent possible under law, the authors of this document have waived all copyright and related or neighboring rights to this work.
