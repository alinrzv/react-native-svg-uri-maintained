# react-native-svg-uri-maintained
Render SVG images in React Native from an URL or a static file

UPDATED SOURCE

The project is built on top of [react-native-svg-uri](https://github.com/alinrzv/react-native-svg-uri-maintained)
, due to original project is not likely being maintained. This fork should be a drop-in replacement and some bug fixing support have being added.

This was tested with

```bash

npx react-native info

  react:
    installed: 18.2.0
    wanted: 18.2.0
  react-native:
    installed: 0.72.1
    wanted: 0.72.1

```

and react-native-svg 9.13.6 (depends on this library)

[react-native-svg](https://github.com/react-native-community/react-native-svg)

Install library from `npm`

```bash
npm install react-native-svg-uri-maintained --save
```

## Props

| Prop | Type | Default | Note |
|---|---|---|---|
| `source` | `ImageSource` |  | Same kind of `source` prop that `<Image />` component has
| `svgXmlData` | `String` |  | You can pass the SVG as String directly
| `fill` | `Color` |  | Overrides all fill attributes of the svg file
| `fillAll` | `Boolean` |  Adds the fill color to the entire svg object

## Known Bugs

- [ANDROID] There is a problem with static SVG file on Android,
  Works OK in debug mode but fails to load the file in release mode.
  At the moment the only workaround is to pass the svg content in the svgXmlData prop.

## <a name="Usage">Usage</a>

Here's a simple example:

```javascript
import SvgUri from 'react-native-svg-uri-maintained';

const TestSvgUri = () => (
  <View style={styles.container}>
    <SvgUri
      width="200"
      height="200"
      source={{uri:'http://thenewcode.com/assets/images/thumbnails/homer-simpson.svg'}}
    />
  </View>
);
```

or a static file

```javascript
<SvgUri width="200" height="200" source={require('./img/homer.svg')} />
```

## Testing
1. Make sure you have installed dependencies with `npm i`
2. Run tests with `npm test`
