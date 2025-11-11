# react-native-theme-provider

A **lightweight theme helper** for React Native that makes adaptive light/dark theming easy and elegant.

---

## Default Color Tokens

| Token             | Purpose              |
|-------------------|----------------------|
| `primaryBg`       | Main background      |
| `secondaryBg`     | Secondary background |
| `primaryText`     | Main text color      |
| `secondaryText`   | Subdued text color   |
| `primaryAccent`   | Accent (primary)     |
| `secondaryAccent` | Accent (secondary)   |
| `err`             | Error / warning      |

> You can customize these in **`themes.json`**.

---

## Usage

### Option A; Direct Color Access:
```js
import { getTheme } from './themeProvider';

const colors = getTheme();

<View style={{ backgroundColor: colors.primaryBg }}>
  <Text style={{ color: colors.primaryText }}>
    Hello themed world!
  </Text>
</View>
```

### Option B; Stylesheet with $tokens:

```js
import { getTheme } from './themeProvider';

const styles = getTheme.create({
  someComponent: {
    backgroundColor: '$primaryBg',
    // auto-resolves → backgroundColor: theme.primaryBg
    color: '$primaryText',
    // auto-resolves → color: theme.primaryText
  }
});
```

### Manual theme override:
```js
const colors = getTheme('light'); // or 'dark'

const styles = getTheme.create({
  card: {
    backgroundColor: '$secondaryBg'
  }
}, 'light');
```
