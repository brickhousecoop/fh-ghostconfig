# Ghost Import Findings

- Imports do not overwrite or update existing members.
	- **Except** for linking member to Stripe
- While exports have a `tiers` column, you _cannot_ import it.
- All imported members with `complimentary_plan` `TRUE` or an active `stripe_customer_id` receive the _first created, unarchived_ tier, with indefinite timeline
	- In our case this is currently `Founding Member`
	- Unarchiving a tier does restore it
	- Proposed process:
		1. Import all Founders
		2. Archive Founding Member tier
		3. Import all regular members & free folks
- Active Stripe subscription supersedes comp column setting
- A member previously deleted (at least recently) will be re-added at whatever tier they were

## Test 002: lapsed Stripe subscriber via Hype

Testing on `j@cobford.com`. Deleted myself from Stripe first, as I had comped myself Hydra.

Imported as free.

## Test 004: active Stripe subscriber that already exists on Ghost

Tested on JOE MACLEOD. Even though he was already a free subscriber he bumped up to Paid, Founding!

## Post-import

- [ ] dfmoskovitz@gmail.com may need to be manually reset to Founding Member (was victim of test 004, deleting now)
