---
icon: dev
---

# Development Environment

## Local Setup

#### Getting Source Code

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

### Using Github Packages for NPM

First, set up a GitHub Personal Access Token (classic) so that we can authenticate with `npm`:

{% embed url="https://youtu.be/tPk_0vZu4hk" %}
Create a Personal Access Token with packages:read permissions.
{% endembed %}

{% hint style="info" %}
Want to know more about GitHub Packages? Head to [https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-npm-registry](https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-npm-registry)
{% endhint %}

Now we can `npm login` with our token to GitHub Packages:

```bash
npm login --scope=@infraregistry --auth-type=legacy --registry=https://npm.pkg.github.com
```

Use your GitHub username and the token as the password:

```bash
$ npm login --scope=@infraregistry --auth-type=legacy --registry=https://npm.pkg.github.com

> Username: USERNAME
> Password: TOKEN
```

Now you can download and public packages to the `@infraregistry` scope using GitHub Packages!

```bash
npm install @infraregistry/types@latest
```

For more information, see [https://github.com/infraregistry/types/pkgs/npm/types](https://github.com/infraregistry/types/pkgs/npm/types).

{% hint style="danger" %}
You must update `.npmrc` in each project root that uses the `@infraregistry` scope so that `npm` knows to contact the GitHub Package Registry with the following:

```properties
engine-strict=true
@infraregistry:registry=https://npm.pkg.github.com
//npm.pkg.github.com/:_auth=${GITHUB_TOKEN}
```

Set the environment variable `GITHUB_TOKEN` in your shell to be that of the token we created earlier.
{% endhint %}

