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


function computeDimensions(props) {
  const { width, height, wrapperWidth, wrapperHeight } = props;
  
  const orientation = computeOrientation(props);
  
  if (orientation.isPortrait) {
    // height is greated than wrapper height, offset height
    const widthRatio = width / wrapperWidth;
    
    const isWidthLessThanWrapper =  widthRatio < 1;
    const isWidthEqual = widthRatio === 1;
    const isWidthGreaterThanWrapper = widthRatio > 1;
  
    const endWidth = wrapperWidth; // scale up, fit to wrapper width
    const endHeight = height / widthRatio; // scale up, now greater than wrapper height
    const max_x = 0;
    const max_y = 0;
    const min_x = 0;
    const min_y = -1 * Math.abs(wrapperHeight - endHeight);
    const offset_x = 0;
    const offset_y = min_y / 2;

    return {
      width: endWidth,
      height: endHeight,
      max_x,
      max_y,
      min_x,
      min_y,
      offset_x,
      offset_y
    }
    
  } else if (orientation.isLandscape) {
    // image width is greater/smaller than wrapper width, offset width
    
    const heightRatio = height / wrapperHeight;

    const endWidth = width / heightRatio; // scale up, fit to wrapper width
    const endHeight = wrapperHeight; // scale up, now greater than wrapper height
    const max_x = 0;
    const max_y = 0;
    const min_x = -1 * Math.abs(wrapperWidth - endWidth);
    const min_y = 0;
    const offset_x = min_x / 2;
    const offset_y = 0;

    return {
      width: endWidth,
      height: endHeight,
      max_x,
      max_y,
      min_x,
      min_y,
      offset_x,
      offset_y
    }
  } else {
    // height is the same, unable to reposition
  }
}



```
