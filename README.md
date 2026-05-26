[![SPASE Monthly Validation](https://github.com/hpde/SMWG/actions/workflows/validate-schedule.yml/badge.svg)](https://github.com/hpde/SMWG/actions/workflows/validate-schedule.yml)
[![SPASE Push Validation](https://github.com/hpde/SMWG/actions/workflows/validate-push.yml/badge.svg)](https://github.com/hpde/SMWG/actions/workflows/validate-push.yml)

# spase-SMWG

SPASE Metadata Working Group (SMWG).

SPASE resource descriptions with the SMWG naming authority.

# How to Use This Repository

If you are a consumer of the metadata simple clone the repostory

````
git clone -b master --single-branch --depth=1 https://github.com/hpde/SMWG
````

If you are a contributor (someone authorized to make changes directly to the repository), clone the repository with:

````
git clone git@github.com:hpde/SMWG.git
````

and use your favorite XML editor and tools to make the changes your want.

After making changes run validation and referential checks on the changed files. 
You can use the [SPASE Resource Tools](https://spase-group.org/tools/resource/) to do this task.
Then push updates (git commit, git push) to the repository.

# How to suggest or make changes

Anyone can suggested changes or updates to a description by loading the description
in the editor, make the changes then click "Submit to Metadata Working Group" at the last step.
You can jump to the last step by clicking "Export" on the list of steps on the left. 

The easiest way to load a description into the SPASE Metadata Editor is to find the 
landing page for a resource description by replacing the "spase://" in the 
SPASE Resource ID with "https://spase-metadata.org/". For example, change

    spase://ESA/NumericalData/PROBA2/LYRA/Flarelist/PT24H

to
    https://spase-metadata.org/ESA/NumericalData/PROBA2/LYRA/Flarelist/PT24H

Navigate to that URL with a browser, the click "Edit" to load the description into the SPASE Metadata editor.

# Validation Actions

GitHub actions are configured for this repository. When a "git push" occurs 
a validation and referential check is performed on the changes or additions 
to the repository since the last push. The status of the action is displayed in the
"SPASE Push Validation" badge at the top of the page. You can view the log of the
validation by viewing the [action workflows](../../actions), clicking on the appropriate workflow
run, then "validate-log" artifict.

The "SPASE Push Validation" is designed to incrementally validate the repository. It assumes
that the repository is valid before the "git push". To perform a whole repository validation
run the "SPASE Manual Validation" action.  To manually run an action go to the [actions](../../actions) page,
select the "SPASE Manual Validation" action, then click on "Run Workflow". For large repositories it 
can take many minutes for the workflow to complete - be patient. Once it is complete the "SPASE Manual Validation"
badge will update.

**Note on badge refresh**: The status portion of a badge is an image. Typically browsers cache images so an 
updated status may not appear immediately. One way to view the current badge is to clear cached images back to when you
last loaded the page, then refresh the page.

**Notes for repository administrator**: There is no garbage collection for workflows. So, its a good practice to
occassionally visit the [action workflows](../../actions) and remove old workflow runs. To remove a run click
the elipses (...) for a work flow and select "Delete workflow run". Typically you would only need the most recent run.
