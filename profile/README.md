# Wagtail Nest

Wagtail Nest houses community maintained third-party packages for Wagtail CMS.

Many third-party Wagtail packages are created and maintained by a single person. This is a risk. Too often single maintainer packages become abandon-ware. The maintainer just doesn’t have the time or motivation to update and release the package.

Wagtail Nest aims to address this problem by housing and maintaining packages collaboratively. Packages will be transferred into the wagtail-nest GitHub organisation. Members of the Wagtail Nest collective will collaboratively maintain and upgrade packages.

By moving the package to Wagtail Nest, the current maintainer (or original author) agrees to collaborate with the other members and will seek consensus when it comes to contentious changes.


## Guidelines

- Be nice
- The primary goal is maintenance. New features are a nice to have
- Release often, every time updates are done.
- Use [SemVer](https://semver.org/). If there are breaking changes, bump the major version.
- Test against Wagtail main, [nightly](https://github.com/wagtail/wagtail/wiki/Nightly-testing-of-official-plugins).
- Automate the release process
- Keep project in sync with the Cookiecutter project template
- Get wider consensus for new features, and consider a major release for them
- Have your code peer reviewed before merging to `main`
- Follow the [Python package maintenance guidelines](https://github.com/wagtail/wagtail/wiki/Python-Package-Maintenance-Guidelines)




## FAQ

*   What packages are accepted as Wagtail Nest packages, and why?
    Similar to [Jazzband](https://github.com/jazzband/), we accept packages for the wider community that are in use and in demand.
    We will allow issues on @wagtail-nest that the community can use to suggest a package to adopt, and the @wagtail-nest members will review.
    Maintenance takes precedence over active development.
    
*   What is the deprecation process?
    Deprecated packages are moved to https://github.com/orgs/wagtail-nest-deprecated.
    The README will start with a clear deprecation warning. With that, the package will no longer be maintained, but existing releases will continue to be available on PyPI. We will not remove releases.
    
    Deprecation will happen via maintainer and community consensus when:
    * there is a newer package that does it better. 
    * Wagtail core gets the functionality. 
    * The package is no longer needed or used.

*   Governance: who gets committer/maintainer access?
    Maintainers can review, merge and release. Maintainers are:
        * The original author(s) (their own repository).
        * Anyone who works at companies with core members (all repositories). Vetted people from companies active in the Wagtail community.
        * Individual member(s) (all repositories)
            
    We trust the original author. 
    We trust the selected companies.
    You can become a individual member by:
    *   Being a regular contributor
    *   By being invited by existing maintainers
    
    In the case of an incident, 3 existing members must approve to revoke a membership.
    
*   Release process
    We automate the package release process. Create a new release in the GitHub UI, and Github actions will create a release and upload the package to PyPI.
    Bumping the version should still be a manual process. Best to open a new release preparation PR with CHANGELOG, version and other miscellanous updates.
    
*   Assurance that package works with current Wagtail (nightly tests against main)?

    All packages must have a nightly build against maintained Wagtail LTS versions, latest release and AND current main. Badges on the README will indicate success or failure.

* Code structure

    All packages must follow the [Python package maintenance guidelines](https://github.com/wagtail/wagtail/wiki/Python-Package-Maintenance-Guidelines).See [cookiecutter-wagtail-package](https://github.com/wagtail/cookiecutter-wagtail-package).
    
*  Code review
    * Anyone can create a pull request to any of the Wagtail Nest repositories. You do not have to be a member to contribute.
    * Only members can merge and release.
    * We have the 4 eyes principle. Don’t merge your own pull request.

*   Who manages the Wagtail Nest Github org? Adding and revoking members?
    In the initial stages, the Wagtail Core team will manage the Nest GitHub org.

*   Who has access to the PyPI keys? Do we need a Wagtail Nest PyPI-account?
    We do not need a shared Wagtail Nest PyPI account, as the goal is to use scoped tokens that can be added by the PyPI package owners. 
    We would ask for at least one other maintainer from the agreed list is added to PyPI with the owner role. We will not mandate access for additional maintainers to PyPI as the automated release process should reduce need for it. We believe this is the most secure way to handle releases.