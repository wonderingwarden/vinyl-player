# Contributing

Contributions that improve usability, accessibility, reliability, or visual quality are welcome.

## Workflow

1. Open an issue describing the problem or proposed change.
2. Create a focused branch from `main`.
3. Keep changes small and preserve the dependency-free architecture unless a dependency is justified.
4. Test the app in a modern browser, including narrow viewport sizes.
5. Open a pull request with a clear summary, motivation, and test notes.

## Quality checklist

- [ ] Existing playback and playlist behavior still works.
- [ ] No new console errors or unhandled promise rejections.
- [ ] Layout remains usable on desktop and mobile.
- [ ] Controls have clear labels and visible focus states.
- [ ] Reduced-motion preferences are respected.
- [ ] No user audio or personal data is sent to a third party.
- [ ] README documentation is updated when behavior changes.

Please do not commit audio files, private data, API keys, build output, or unrelated generated assets.
