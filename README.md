# Custom YouTube Video Player

A lightweight, customizable YouTube video player component with clean UI and precise playback control.


## Features

- ✅ **Custom Play/Pause Controls**: Elegant, minimalist player controls
- ✅ **Precise Timestamp Control**: Set exact video end points
- ✅ **Smart Autoplay**: Starts muted (browser-friendly) until user interaction
- ✅ **Responsive Design**: Maintains aspect ratio across device sizes
- ✅ **User-Friendly Interactions**: Intuitive hover effects and state management
- ✅ **Zero Dependencies**: No external libraries required (beyond YouTube API)
- ✅ **Lightweight**: Minimal code footprint
- ✅ **Easy Customization**: Simple to style and adapt

## Installation

### Option 1: Direct Include

Simply copy the HTML and script code from `youtube-player.html` into your project.

### Option 2: Import as Module

1. Copy the files to your project
2. Include the HTML in your page:

```html
<div id="youtube-player-container"></div>
<script src="path/to/youtube-player.js"></script>
<script>
  document.addEventListener('DOMContentLoaded', function() {
    initYouTubePlayer('youtube-player-container', 'YOUR_VIDEO_ID', 120); // 120 seconds cutoff
  });
</script>
```

## Usage

### Basic Implementation

```html
<!--
  Include the player in your HTML
  Replace "MqXZ1QDHGIs" with your YouTube video ID
-->
<header class="custom-video-header" style="overflow: hidden; background-color: black; position: relative; border-radius: 10px; box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);">
  <div id="video-container" style="position: relative; aspect-ratio: 4/3; overflow: hidden; border-radius: 10px; height: 140%; box-shadow: 0 8px 16px rgba(0, 0, 0, 0.15);">
    <iframe 
      id="youtubeVideo"
      src="https://www.youtube.com/embed/MqXZ1QDHGIs?enablejsapi=1&mute=1&controls=0&loop=0&playsinline=1&rel=0&modestbranding=1&iv_load_policy=3&showinfo=0&autoplay=1&end=120" 
      frameborder="0" 
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
      allowfullscreen
      style="position: absolute; top: 50%; left: 50%; width: 180%; height: 180%; transform: translate(-50%, -50%);"
    ></iframe>
    
    <!-- Custom play/pause button -->
    <button id="playPauseButton" style="position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%); z-index: 10; background: rgba(255,255,255,0.9); border: none; border-radius: 50%; width: 80px; height: 80px; cursor: pointer; display: flex; justify-content: center; align-items: center; transition: opacity 0.3s ease; opacity: 1;">
      <svg id="playIcon" width="40" height="40" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
        <polygon points="5 3 19 12 5 21 5 3"></polygon>
      </svg>
      <svg id="pauseIcon" width="40" height="40" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" style="display: none;">
        <line x1="6" y1="4" x2="6" y2="20"></line>
        <line x1="18" y1="4" x2="18" y2="20"></line>
      </svg>
    </button>
  </div>
</header>

<!-- Include the JavaScript -->
<script src="path/to/youtube-player.js"></script>
```

### Customization

Modify the following parameters to customize your player:

1. **Video ID**: Change the YouTube video ID in the iframe src URL
   ```
   Replace 'MqXZ1QDHGIs' with your YouTube video ID
   ```

2. **End Time**: Adjust the `endTime` variable in JavaScript to set your cutoff point
   ```javascript
   var endTime = 120; // Set to your desired end time in seconds
   ```

3. **Styling**: Customize the appearance by modifying the inline styles or adding your own CSS classes

4. **Auto-restart**: Uncomment the auto-restart code if you want the video to loop
   ```javascript
   // In the onPlayerReady function:
   // player.seekTo(0);
   // isPaused = true;
   // updatePlayPauseButton();
   ```

## Configuration Options

| Parameter | Description | Default |
|-----------|-------------|---------|
| Video ID | YouTube video identifier | MqXZ1QDHGIs |
| End Time | Timestamp to end video (seconds) | 120 |
| Aspect Ratio | Container aspect ratio | 4/3 |
| Autoplay | Start playing automatically (muted) | true |
| Controls | Show YouTube native controls | false |
| Related Videos | Show related videos when ended | false |

## Browser Compatibility

- Chrome 53+
- Firefox 63+
- Safari 10.1+
- Edge 79+
- Opera 40+

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## Acknowledgments

- Uses the [YouTube IFrame API](https://developers.google.com/youtube/iframe_api_reference)
- Inspired by minimal design principles and user-friendly video interfaces
