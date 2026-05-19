# How This File Is Used

In general, upcoming/unreleased behavior changes are described here. For details
on the process that this file is part of, see
`rs/nervous_system/changelog_process.md`.


# Next Upgrade Proposal

## Added

* Added an optional `subnet_admins` field to `UpdateSubnetPayload`, allowing NNS
  proposals to set, replace, or clear the list of admins of a subnet. `None`
  leaves the existing list unchanged; `Some(vec![])` clears it; `Some(vec![..])`
  replaces it.

## Changed

* Moved the max-10 cap on `subnet_admins` from a check local to
  `update_subnet_admins` into a registry invariant, so the cap is now enforced
  uniformly on every mutation that touches a subnet record.

## Deprecated

## Removed

## Fixed

## Security
