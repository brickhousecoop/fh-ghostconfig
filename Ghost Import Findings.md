# Ghost Import Findings

- Imports do not overwrite or update existing members.
- While exports have a `tiers` column, you _cannot_ import it.
- All imported members with `complimentary_plan` `TRUE` receive the _first created_ tier, with indefinite timeline
	- In our case this is currently `Founding Member`
	- I have not yet tested what happens if we archive and/or reactivate that tier.

## Test: lapsed Stripe subscriber via Hype

Testing on `j@cobford.com`. Deleted myself from Stripe first, as I had comped myself Hydra.

Imported as free.
