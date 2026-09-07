# Firebase Rules Record

Last verified: 2026-09-07
Firebase project: `onepieceeastbluearc`
Database: Cloud Firestore `(default)` in `asia-southeast1`

## Deployed policy

### `leaderboard/{player}`

- Public read is allowed for the in-game leaderboard.
- Create requires `name`, `score`, and `ts`.
- The stored `name` must equal the document ID.
- `score` must be numeric and non-negative.
- Updates must preserve the player identity and cannot reduce the score.
- Delete is denied because no delete rule is granted.

### `saves/{player}`

- Existing public read/write/delete behavior is temporarily preserved.
- This is required by the current reset flow in `index.html`.
- Harden only after the reset implementation is redesigned and regression-tested.

## Operational note

The rules were published in Firebase Console and read back successfully. The production HTML was not changed.
