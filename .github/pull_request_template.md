## Summary

Describe what changed.

## Motivation

Explain the problem this change solves and why this approach was chosen.

## Related issues

<!-- Use "Closes #123" when this PR should close an issue. -->

## Compatibility impact

Describe any effect on:

- Public Rust APIs
- Supported ESP chips or boards
- Cargo features
- Device-to-host protocols
- Serialized CSI or configuration formats
- Firmware, server, or client compatibility

Write "None" when there is no compatibility impact.

## Testing

List the exact commands, targets, features, and configurations used to verify
the change.

```sh
# Examples — replace these with the commands you actually ran:
# cargo fmt --all -- --check
# cargo check --workspace
# cargo test --workspace
# cargo clippy --workspace --all-targets --all-features -- -D warnings
````

## Hardware validation

For embedded or device-dependent changes, include:

- ESP chip and board
- Rust target
- Enabled Cargo features
- Flashing method
- Test setup
- Observed result

Write "Not applicable" when no hardware validation is required.

## Checklist

- [ ] The change is focused and contains no unrelated edits.
- [ ] `cargo fmt --all -- --check` passes.
- [ ] Relevant build, Clippy, and test commands pass for the affected targets and features.
- [ ] New behavior is covered by tests or a focused reproducer where practical.
- [ ] Relevant ESP hardware was tested, or hardware testing is not applicable.
- [ ] Public API, protocol, or data-format changes are documented, or this is not applicable.
- [ ] User-facing and contributor documentation was updated where necessary.
- [ ] Logs, examples, and fixtures contain no credentials or sensitive information.
