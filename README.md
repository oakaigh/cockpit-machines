# cockpit-machines

This is the [Cockpit](https://cockpit-project.org/) user interface for virtual machines

## Technologies

- cockpit-machines communicates to libvirt through its [dbus API](https://libvirt.org/dbus.html).

# Automated release

Releases are automated using [Cockpituous release](https://github.com/cockpit-project/cockpituous/tree/master/release)
which aims to fully automate project releases to GitHub, Fedora, Ubuntu, COPR, Docker
Hub, and other places. The intention is that the only manual step for releasing
a project is to create a signed tag for the version number.

The release steps are controlled by the
[cockpituous-release](./cockpituous-release) script.

Pushing the release tag triggers the [release.yml](.github/workflows/release.yml)
[GitHub action](https://github.com/features/actions) workflow. This uses the
[cockpit-project organization secrets](https://github.com/organizations/cockpit-project/settings/secrets).

# Automated maintenance

It is important to keep your [NPM modules](./package.json) up to date, to keep
up with security updates and bug fixes. This is done with the
[npm-update bot script](https://github.com/cockpit-project/bots/blob/master/npm-update)
which is run weekly or upon [manual request](https://github.com/cockpit-project/cockpit-machines/actions) through the
[npm-update.yml](.github/workflows/npm-update.yml) [GitHub action](https://github.com/features/actions).

Similarly, translations are refreshed every Tuesday evening (or manually) through the
[po-refresh.yml](.github/workflows/po-refresh.yml) action.
