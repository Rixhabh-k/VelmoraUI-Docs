# Velmora UI

A reusable animation and interaction library for building modern, expressive web interfaces with ready-to-use React components and customizable effects.

## Installation

```bash
npm install velmora
```

Import the Velmora stylesheet:

```jsx
import "velmora/styles.css";
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
  UploadButton
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
  UploadButton
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
| `filename`         | `"File.pdf"`     | File name displayed by the button  |
| `buttonText`       | `"Upload"`       | Initial button label               |
| `uploadingText`    | `"Uploading..."` | Label shown during upload          |
| `completedText`    | `"Completed"`    | Label shown after upload completes |
| `uploadDuration`   | `3000`           | Upload animation duration in ms    |
| `completeDuration` | `2000`           | Completion state duration in ms    |
| `buttonColor`      | `"#3bafda"`      | Button background color            |
| `progressColor`    | `"#2d334c"`      | Upload progress color              |
| `className`        | `""`             | Custom CSS class                   |

# Current Components

## Buttons

* Magnetic Button
* Flip Button
* Fill Button
* 3D Button
* Submit Button
* Position Aware Button
* Upload Button

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
