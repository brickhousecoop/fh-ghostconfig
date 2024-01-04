# Ghost Import Findings

- While exports have a `tiers` column, you _cannot_ import it.
- All imported members with `complimentary_plan` `TRUE` receive the _first created_ tier.
	- In our case this is currently `Founding Member`
	- I have not yet tested what happens if we archive and/or reactivate that tier.
