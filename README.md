# Velmora UI

A reusable animation and interaction library for building modern, expressive web interfaces with ready-to-use React components and customizable effects.

## Installation

```bash
npm install velmora
```

Import the Velmora stylesheet:

```jsx
import "velmora/style.css";
```

Import components:

```jsx
import {
  MagneticButton,
  FlipButton,
  FillButton,
  ThreeDButton,
  SubmitButton,
  PositionAwareButton,
  UploadButton,
  TypeWriterText,
  TextScramble,
  ShadowText,
  WaveText,
  MagicText
} from "velmora";
```

## Basic Usage

```jsx
import {
  MagneticButton,
  FlipButton,
  FillButton,
  ThreeDButton,
  SubmitButton,
  PositionAwareButton,
  UploadButton,
  TypeWriterText,
  TextScramble,
  ShadowText,
  WaveText,
  MagicText
} from "velmora";

import "velmora/styles.css";

function App() {
  return (
    <div>
      <MagneticButton>Magnetic</MagneticButton>

      <FlipButton front="FRONT" back="BACK" />

      <FillButton>Hover Me</FillButton>

      <ThreeDButton front="FRONT" back="BACK" />

      <SubmitButton />

      <PositionAwareButton>
        Position Aware
      </PositionAwareButton>

      <UploadButton />

      <TypeWriterText />

      <TextScramble />

      <ShadowText>
        COLORS
      </ShadowText>

      <WaveText>
        WAVES
      </WaveText>

      <MagicText />
    </div>
  );
}

export default App;
```

## Custom Styling

Velmora provides the animation behavior while users remain in control of the visual design through `className`.

```jsx
<MagneticButton className="my-button">
  Magnetic
</MagneticButton>
```

```css
.my-button {
  width: 220px;
  height: 60px;
  border-radius: 30px;
  border: 2px solid black;
  background: purple;
  color: white;
  font-size: 18px;
}
```

# Buttons

## Magnetic Button

A magnetic interaction where the button follows the cursor within a specified radius.

```jsx
<MagneticButton
  strength={0.35}
  radius={150}
  ease={0.15}
  className="magnetic-button"
>
  Magnetic
</MagneticButton>
```

Props:

| Prop        | Default      | Description         |
| ----------- | ------------ | ------------------- |
| `children`  | `"Hover Me"` | Button content      |
| `strength`  | `0.35`       | Magnetic strength   |
| `radius`    | `150`        | Activation radius   |
| `ease`      | `0.15`       | Movement smoothness |
| `className` | `""`         | Custom CSS class    |

## Flip Button

A 3D-style text flip effect.

```jsx
<FlipButton
  front="FRONT"
  back="BACK"
  duration={500}
  frontColor="#323237"
  backColor="#adadaf"
  textColor="#adadaf"
  backTextColor="#323237"
/>
```

Props:

| Prop            | Default     | Description              |
| --------------- | ----------- | ------------------------ |
| `front`         | `"Front"`   | Front text               |
| `back`          | `"Back"`    | Back text                |
| `duration`      | `500`       | Animation duration in ms |
| `frontColor`    | `"#323237"` | Front background         |
| `backColor`     | `"#adadaf"` | Back background          |
| `textColor`     | `"#adadaf"` | Front text color         |
| `backTextColor` | `"#323237"` | Back text color          |
| `className`     | `""`        | Custom CSS class         |

## Fill Button

An expanding fill effect that fills the button on hover.

```jsx
<FillButton
  fillColor="#38146a"
  textColor="#fff"
  hoverTextColor="#fff"
  duration={350}
  className="fill-button"
>
  Hover Me
</FillButton>
```

Props:

| Prop             | Default       | Description         |
| ---------------- | ------------- | ------------------- |
| `children`       | `"Hover Me!"` | Button content      |
| `fillColor`      | `"#38146a"`   | Fill color          |
| `textColor`      | `"#fff"`      | Default text color  |
| `hoverTextColor` | `"#fff"`      | Hover text color    |
| `duration`       | `350`         | Fill duration in ms |
| `className`      | `""`          | Custom CSS class    |

## 3D Button

A 3D box-style button that rotates around its axis to reveal another face.

```jsx
<ThreeDButton
  front="FRONT"
  back="BACK"
  duration={500}
  frontColor="#323237"
  backColor="#adadaf"
  textColor="#adadaf"
  backTextColor="#323237"
/>
```

Props:

| Prop            | Default     | Description        |
| --------------- | ----------- | ------------------ |
| `front`         | `"Front"`   | Front face content |
| `back`          | `"Back"`    | Back face content  |
| `duration`      | `500`       | Rotation duration  |
| `frontColor`    | `"#323237"` | Front background   |
| `backColor`     | `"#adadaf"` | Back background    |
| `textColor`     | `"#adadaf"` | Front text color   |
| `backTextColor` | `"#323237"` | Back text color    |
| `className`     | `""`        | Custom CSS class   |

## Submit Button

A submit interaction with idle, loading, and success states.

```jsx
<SubmitButton
  idleText="SUBMIT"
  loadingText="SENDING..."
  successText="SUBMITTED"
  duration={2250}
  successDuration={1250}
  color="#1ECD97"
  loadingColor="#bbbbbb"
  successColor="#471ecd"
/>
```

Props:

| Prop              | Default        | Description             |
| ----------------- | -------------- | ----------------------- |
| `idleText`        | `"SUBMIT"`     | Initial text            |
| `loadingText`     | `"SENDING..."` | Loading label/API value |
| `successText`     | `"SUBMITTED"`  | Success label/API value |
| `duration`        | `2250`         | Loading duration        |
| `successDuration` | `1250`         | Success duration        |
| `color`           | `"#1ECD97"`    | Primary color           |
| `loadingColor`    | `"#bbbbbb"`    | Spinner color           |
| `successColor`    | `"#471ecd"`    | Success color           |
| `className`       | `""`           | Custom CSS class        |

## Position Aware Button

A cursor-position-aware circular fill effect. The fill originates from the cursor position.

```jsx
<PositionAwareButton
  fillColor="#38146a"
  textColor="#38146a"
  hoverTextColor="#fff"
  duration={400}
  className="position-button"
>
  Position Aware
</PositionAwareButton>
```

Props:

| Prop             | Default            | Description         |
| ---------------- | ------------------ | ------------------- |
| `children`       | `"POSITION AWARE"` | Button content      |
| `fillColor`      | `"#333"`           | Circular fill color |
| `textColor`      | `"#fff"`           | Default text color  |
| `hoverTextColor` | `"#fff"`           | Hover text color    |
| `duration`       | `400`              | Fill duration in ms |
| `className`      | `""`               | Custom CSS class    |

## Upload Button

An animated upload interaction with uploading progress and completion states.

```jsx
<UploadButton
  filename="Document.pdf"
  buttonText="Upload"
  uploadingText="Uploading..."
  completedText="Completed"
  uploadDuration={3000}
  completeDuration={2000}
  buttonColor="#3bafda"
  progressColor="#2d334c"
  className="my-upload"
/>
```

Props:

| Prop               | Default          | Description                        |
| ------------------ | ---------------- | ---------------------------------- |
| `filename`         | `"File.pdf"`     | File name displayed by the button |
| `buttonText`       | `"Upload"`       | Initial button label               |
| `uploadingText`    | `"Uploading..."` | Label shown during upload          |
| `completedText`    | `"Completed"`    | Label shown after upload completes |
| `uploadDuration`   | `3000`           | Upload animation duration in ms    |
| `completeDuration` | `2000`           | Completion state duration in ms    |
| `buttonColor`      | `"#3bafda"`      | Button background color            |
| `progressColor`    | `"#2d334c"`      | Upload progress color              |
| `className`        | `""`             | Custom CSS class                   |

# Text Components

## TypeWriter Text

A typewriter-style text animation that types, pauses, and deletes phrases before moving to the next phrase.

```jsx
<TypeWriterText
  words={["Hello", "World", "Velmora"]}
  typingSpeed={100}
  deletingSpeed={50}
  pauseDuration={1000}
  className="typewriter-text"
/>
```

Props:

| Prop             | Default | Description                       |
| ---------------- | ------- | --------------------------------- |
| `words`          | `[]`    | Array of words or phrases         |
| `typingSpeed`    | `100`   | Typing speed in milliseconds      |
| `deletingSpeed`  | `50`    | Deleting speed in milliseconds    |
| `pauseDuration`  | `1000`  | Pause duration in milliseconds    |
| `className`      | `""`    | Custom CSS class                  |

## Text Scramble

A text scrambling effect that transitions between phrases using randomized characters.

```jsx
<TextScramble
  phrases={[
    "Build",
    "Create",
    "Animate"
  ]}
  pauseDuration={800}
  className="scramble-text"
/>
```

Props:

| Prop            | Default | Description                        |
| --------------- | ------- | ---------------------------------- |
| `phrases`       | `[]`    | Array of phrases to cycle through  |
| `pauseDuration` | `800`   | Pause duration in milliseconds     |
| `className`     | `""`    | Custom CSS class                   |

## Shadow Text

A mouse-reactive text effect where the shadow follows the cursor with smooth movement and dynamic color.

```jsx
<ShadowText
  shadowOffset={100}
  shadowOpacity={0.5}
  shadowSaturation={50}
  shadowLightness={50}
  smoothing={0.08}
  className="shadow-text"
>
  COLORS
</ShadowText>
```

Props:

| Prop               | Default   | Description                |
| ------------------ | --------- | -------------------------- |
| `children`         | `"COLORS"` | Text content              |
| `shadowOffset`     | `100`     | Shadow movement range      |
| `shadowOpacity`    | `0.5`     | Shadow opacity             |
| `shadowSaturation` | `50`      | Shadow color saturation    |
| `shadowLightness`  | `50`      | Shadow color lightness     |
| `smoothing`        | `0.08`    | Movement smoothness        |
| `className`        | `""`      | Custom CSS class           |

## Wave Text

A layered 3D text effect with multiple colored text copies that react smoothly to cursor movement.

```jsx
<WaveText
  colors={[
    "#f24c00",
    "#9792e3",
    "#fc7a1e",
    "#eda96d"
  ]}
  depth={12}
  rotate={3}
  skew={3}
  perspective={500}
  smoothing={0.2}
  className="wave-text"
>
  WAVES
</WaveText>
```

Props:

| Prop          | Default     | Description                    |
| ------------- | ----------- | ------------------------------ |
| `children`    | `"WAVES"`   | Text content                   |
| `colors`      | `4 colors`  | Colors used for text layers    |
| `depth`       | `12`        | Depth between text layers      |
| `rotate`      | `3`         | Rotation intensity             |
| `skew`        | `3`         | Skew intensity                 |
| `perspective` | `500`       | 3D perspective distance       |
| `smoothing`   | `0.2`       | Cursor movement smoothness     |
| `className`   | `""`        | Custom CSS class               |

## Magic Text

A highlighted text effect with animated gradient colors and randomly appearing decorative stars.

```jsx
<MagicText
  beforeText="Sometimes I'll start a line of code and I"
  magicText="don't even know"
  afterText="where it's going."
  colors={[
    "#7b1fa2",
    "#673ab7",
    "#f48fb1"
  ]}
  starCount={3}
  starInterval={1000}
  starSize={24}
  className="magic-text"
/>
```

Props:

| Prop           | Default     | Description                     |
| -------------- | ----------- | ------------------------------- |
| `beforeText`   | `""`        | Text displayed before the effect |
| `magicText`    | `""`        | Main animated text              |
| `afterText`    | `""`        | Text displayed after the effect  |
| `colors`       | `3 colors`  | Gradient colors                 |
| `starCount`    | `3`         | Number of decorative stars      |
| `starInterval` | `1000`      | Star animation interval in ms   |
| `starSize`     | `24`        | Star size in pixels             |
| `className`    | `""`        | Custom CSS class                |

# Current Components

## Buttons

* Magnetic Button
* Flip Button
* Fill Button
* 3D Button
* Submit Button
* Position Aware Button
* Upload Button

## Text Components

* TypeWriter Text
* Text Scramble
* Shadow Text
* Wave Text
* Magic Text

# Animation Philosophy

Velmora does not force JavaScript for every animation.

CSS is used where it is sufficient. JavaScript is used when runtime interaction is required, such as cursor position, dynamic movement, state changes, and user-controlled thresholds.

# Development

Velmora includes a playground environment for testing animations and components before release.

The playground is for development/testing and is not required by package users.

# Roadmap

* More button animations
* Text animations
* Image animations
* Card interactions
* Cursor effects
* Scroll animations
* Page transitions
* Advanced interactive effects
* Additional customization options

# Contributing

Bug reports, suggestions, and contributions are welcome.

Open an issue or submit a pull request.

# License

MIT License
