---
icon: dev
---

# Development Environment

## Local Setup

We'll use the [polyrepo](https://github.com/polyrepopro/polyrepo) cli to pull down all of the repositories locally.

{% hint style="info" %}
[polyrepo](https://github.com/polyrepopro/polyrepo) is a workspace synchronization tool that uses a **polyrepo** approach which gives us more flexibility and reduces the complexity over traditional monorepos.
{% endhint %}

Install the [polyrepo](https://github.com/polyrepopro/polyrepo) cli:

```bash
go install github.com/polyrepopro/polyrepo@latest
```

and run the following to initialize the workspace:

```bash
polyrepo init --path ~/workspace/.polyrepo.yaml --url https://raw.githubusercontent.com/infraregistry/workspace/refs/heads/main/.polyrepo.yaml?token=GHSAT0AAAAAACW3AGD6HULOTO5U5DEAPF2IZYCVW2Q 
polyrepo sync
```

Now you can open up the `~/workspace/infraregistry` directory in your IDE.

### Pushing Changes

First, commit your changes across all repos:

```bash
polyrepo commit --message "implemented feature abc"
```

Now that your changes are committed we can push to github:

```bash
polyrepo push
```
