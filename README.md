# AquaNIS

## Rationale

Mapping of AquaNIS data to [Darwin Core](https://dwc.tdwg.org/) data standard.

**IMPORTANT**: at this moment this is a work in progress. The mapping is not yet complete. Also, the repository doesn't contain the software to convert AquaNIS data to Darwin Core. The repository is at the moment only meant to be a **reference** for the mapping of AquaNIS data to Darwin Core.

Mapping is now a Markdown file in `references`. If the software to convert AquaNIS data to Darwin Core is developed, it will be added to the `src` directory.

## Repo structure

The repository structure is based on [Cookiecutter Data Science](http://drivendata.github.io/cookiecutter-data-science/). Files and directories indicated with `GENERATED` (if any) should not be edited manually.

```
├── README.md              : Description of this repository
├── LICENSE                : Repository license
├── AquaNIS.Rproj          : RStudio project file
├── .gitignore             : Files and directories to be ignored by git
└── references             : Data dictionaries, manuals, and all other explanatory materials.
    ├── AquaNIS_definitions_2025-03-21_GuardIAS.pdf   : data scheme and data dictionaries in use in AquaNIS.
    ├── AquaNIS_ Dreissena bugensis_Ireland.pdf   : Example of AquaNIS data
    └── AquaNIS_to_DarwinCore.md : Markdown file with the mapping of AquaNIS data to Darwin Core.
```
