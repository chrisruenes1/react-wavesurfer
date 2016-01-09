# react-wavesurfer

_This project is under active development, the functionality is still pretty rugged. Any contribution is greatly appreciated_

Implemented so far:

* WaveSurfer instantiation options can be set by component props
* WaveSurfer events trigger callbacks passed in as props (prefixed with on and capitalised, e.g. the event *ready* triggers the *onReady* prop callback)
* WaveSurver position, playing status and audioFile can be dynamically set by props

Todos:

* Integrate Timeline, Regions, Minimap
* Tests!

## Usage

```javascript
import React from 'react';
import ReactDOM from 'react-dom';
import Wavesurfer from 'react-wavesurfer';

class MyComponent extends React.Component {
  render() {
    let props = this.state;
    return (
      <div>
        <Wavesurfer
          audioFile: 'path/to/audio/file.mp3'
          pos: 20,
          playing: false
        />
      </div>
      );
  }
}
```

## Props

Prop name | type | description
--- | --- | ---
`playing` | bool | controls wether the player is playing
`pos` | number | position of playback in seconds
`audioFile` | string/blob | the audio to render, can be set after the component was mounted
`options` | object | the instantiation options for wavesurfer. See [documentation of wavesurfer.js](https://github.com/katspaugh/wavesurfer.js#wavesurfer-options). The defaults values are the default values of wavesurfer.js

### Callback props
Prop name | description
--- | ---
`onAudioprocess` | Hooks into the respective wavesurfer.js event. See [documentation of wavesurfer.js](https://github.com/katspaugh/wavesurfer.js#wavesurfer-events)
`onError` | See above
`onFinish` | See above
`onLoading` | See above
`onMouseup` | See above
`onPause` | See above
`onPlay` | See above
`onReady` | See above
`onScroll` | See above
`onSeek` | See above
`onZoom` | See above

