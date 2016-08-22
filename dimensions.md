```javascript

function computeOrientation(props) {

  const { width, height, wrapperWidth, wrapperHeight } = props;
  const imageAspectRatio = width / height;
  const wrapperAspectRatio = wrapperWidth / wrapperHeight;
  
  const isPortrait = imageAspectRatio < wrapperAspectRatio;
  const isLandscape = imageAspectRatio > wrapperAspectRatio;
  const isPerfectFit = imageAspectRatio === wrapperAspectRatio;
  
  return {
    isPortrait,
    isLandscape,
    isPerfectFit
  }
}



```
