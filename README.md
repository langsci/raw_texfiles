# raw_texfiles

This repository contains the tex source code of all books published by Language Science Press. This includes makefiles and BibTeX bibliographies, but excludes
binary files and input for graphics, etc.


## Curation

This repository is curated using the `linglit` package. To update the content,
run
```shell
linglit update langsci .
```

Note that this requires the [GitHub shell client gh](https://cli.github.com/)
and a [GitHub personal access token](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token) available
to `gh` to allow for a sufficient number of API requests.

