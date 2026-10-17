# React Native TypeScript + NativeWind Starter

A minimal Expo + Expo Router + TypeScript + NativeWind starter with a scalable folder structure.
It intentionally contains no business features and no prebuilt UI beyond an empty screen.

## Recommended setup

Create the Expo Router TypeScript app first:

```bash
npx create-expo-app@latest my-mobile-app --template tabs
cd my-mobile-app
```

Install NativeWind v4 (stable) and its dependencies:

```bash
npm install nativewind@4.2.7
npx expo install react-native-reanimated react-native-safe-area-context
npm install -D tailwindcss@^3.4.17 babel-preset-expo
```

Then copy the `src/` directory and configuration files from this starter into your project, replacing files when prompted. Keep the Expo-generated `package.json`, lockfile, and `app.json`; make sure `package.json` has `"main": "expo-router/entry"` and `app.json` uses the Expo Router plugin.

Run:

```bash
npx expo start --clear
```

## Structure

```text
src/
├── app/                 # Expo Router routes and layouts
├── components/
│   ├── common/          # Shared app-level components
│   └── ui/              # Small reusable UI primitives
├── config/              # Environment and app configuration
├── constants/           # App-wide constants
├── features/            # Feature/domain modules
├── hooks/               # Shared custom hooks
├── services/
│   ├── api/             # API client and endpoint modules
│   └── storage/         # Local persistence adapters
├── store/               # Global state (add a library only when needed)
├── types/               # Shared TypeScript types
└── utils/               # Pure helper functions
```

Empty folders include `.gitkeep` so they remain in version control.

## Notes

- Keep feature-specific components, hooks, services, and types inside `src/features/<feature-name>/` as the app grows.
- Keep `src/components/ui/` for generic reusable primitives, not feature-specific UI.
- Do not add state management, API libraries, authentication, or other dependencies until the app needs them.
- This starter targets NativeWind v4 stable. NativeWind v5 is currently a prerelease and has a different setup.
