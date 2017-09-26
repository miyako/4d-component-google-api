# 4d-component-google-api
Example of calling Google APIs from 4D

### Version

<img src="https://cloud.githubusercontent.com/assets/1725068/18940648/2192ddba-8645-11e6-864d-6d5692d55717.png" width="32" height="32" />

**Note**: most critical features are ``HTTP Request`` and ``C_OBJECT``.

Example calls Google Cloud Vision (OCR) to read text in image.

<?xml version="1.0" encoding="utf-8"?>
<!-- Generator: Adobe Illustrator 18.0.0, SVG Export Plug-In . SVG Version: 6.00 Build 0)  -->
<!DOCTYPE svg PUBLIC "-//W3C//DTD SVG 1.1//EN" "http://www.w3.org/Graphics/SVG/1.1/DTD/svg11.dtd">
<svg version="1.1" id="Layer_1" xmlns:sketch="http://www.bohemiancoding.com/sketch/ns"
	 xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" width="49px" height="49px" xml:space="preserve">
<path id="Fill-7" sketch:type="MSShapeGroup" fill="#AB47BC" d="M24,0C10.7,0,0,10.7,0,24s10.7,24,24,24s24-10.7,24-24S37.3,0,24,0"
	/>
<path id="Fill-8" sketch:type="MSShapeGroup" fill="#BA68C8" d="M40.5,24c0,9.1-7.4,16.5-16.5,16.5S7.5,33.1,7.5,24S14.9,7.5,24,7.5
	S40.5,14.9,40.5,24"/>
<path id="Fill-9" sketch:type="MSShapeGroup" fill="#FFFFFF" d="M31,34H17v-4l4.7-4.6c1.4-1.5,2.3-2.5,2.7-3c0.4-0.5,0.7-1,0.9-1.4
	c0.2-0.4,0.3-0.8,0.3-1.2c0-0.5-0.2-0.9-0.5-1.2c-0.3-0.3-0.8-0.5-1.4-0.5c-0.6,0-1.3,0.2-1.9,0.5c-0.6,0.4-1.4,0.9-2.2,1.6l-3-3.5
	c1-0.9,1.9-1.6,2.6-2c0.7-0.4,1.5-0.7,2.3-0.9c0.8-0.2,1.8-0.3,2.8-0.3c1.3,0,2.5,0.2,3.5,0.7c1,0.5,1.8,1.1,2.4,2
	C30.7,17,31,18,31,19c0,0.8-0.1,1.5-0.3,2.2c-0.2,0.7-0.5,1.3-0.9,2c-0.4,0.6-1,1.3-1.6,2c-0.7,0.7-2.1,2.1-4.3,4.1v0.1H31V34"/>
<path id="Fill-10" sketch:type="MSShapeGroup" fill="#FFFFFF" d="M33.2,3.8l0.9,0.5l-0.7,1.2l1,0.6l0.7-1.2l0.9,0.5l-1.9,3.3
	l-0.9-0.5l0.8-1.4l-1-0.6l-0.8,1.4l-0.9-0.5L33.2,3.8"/>
<path id="Fill-11" sketch:type="MSShapeGroup" fill="#FFFFFF" d="M28.1,2.1l2.8,0.8l-0.2,0.8l-0.9-0.2L29,6.4l-1-0.3l0.8-2.9L27.9,3
	L28.1,2.1"/>
<path id="Fill-12" sketch:type="MSShapeGroup" fill="#FFFFFF" d="M22.3,1.7l1,0l0,2.2c0,0.3,0,0.5,0.1,0.6c0.1,0.1,0.2,0.2,0.4,0.2
	c0.2,0,0.4-0.1,0.5-0.2s0.1-0.3,0.2-0.6l0-2.2l1,0l0,2.3c0,0.5-0.2,0.9-0.4,1.2c-0.3,0.3-0.7,0.4-1.2,0.4c-0.5,0-0.9-0.1-1.2-0.4
	c-0.3-0.3-0.4-0.7-0.4-1.2L22.3,1.7"/>
<path id="Fill-13" sketch:type="MSShapeGroup" fill="#FFFFFF" d="M14.2,44.2l-0.9-0.5l0.7-1.2l-1-0.6l-0.7,1.2l-0.9-0.5l1.9-3.3
	l0.9,0.5l-0.8,1.4l1,0.6l0.8-1.4l0.9,0.5L14.2,44.2"/>
<path id="Fill-14" sketch:type="MSShapeGroup" fill="#FFFFFF" d="M19.3,45.9l-2.8-0.8l0.2-0.8l0.9,0.2l0.8-2.9l1,0.3l-0.8,2.9
	l0.9,0.2L19.3,45.9"/>
<path id="Fill-15" sketch:type="MSShapeGroup" fill="#FFFFFF" d="M25.1,46.3l-1,0l0-2.2c0-0.3,0-0.5-0.1-0.6
	c-0.1-0.1-0.2-0.2-0.4-0.2c-0.2,0-0.4,0.1-0.5,0.2c-0.1,0.1-0.1,0.3-0.2,0.6l0,2.2l-1,0l0-2.3c0-0.5,0.2-0.9,0.4-1.2
	c0.3-0.3,0.7-0.4,1.2-0.4c0.5,0,0.9,0.1,1.2,0.4c0.3,0.3,0.4,0.7,0.4,1.2L25.1,46.3"/>
<path id="Fill-16" sketch:type="MSShapeGroup" fill="#FFFFFF" d="M29.1,41.6l0,0.7l-1.2,0.3L27.5,42l-1.1,0.3l2.2,3.4l1.3-0.3l0.2-4
	L29.1,41.6L29.1,41.6z M28.9,44.5c-0.1-0.2-0.2-0.4-0.3-0.5l-0.3-0.6l0.8-0.2c0,0.6,0,1,0,1.2c0,0.2,0,0.4,0,0.5
	C29.1,44.9,29,44.7,28.9,44.5L28.9,44.5z"/>
<path id="Fill-17" sketch:type="MSShapeGroup" fill="#FFFFFF" d="M35.5,40.7c-0.3-0.6-0.7-0.9-1.2-1c-0.4-0.1-0.9,0-1.4,0.3
	c-0.5,0.3-0.8,0.7-1,1.1c-0.1,0.4,0,1,0.3,1.5c0.3,0.6,0.7,0.9,1.1,1c0.4,0.1,0.9,0,1.5-0.3c0.5-0.3,0.8-0.7,0.9-1.1
	C35.9,41.7,35.8,41.2,35.5,40.7L35.5,40.7z M34.4,42.6c-0.2,0.1-0.4,0.1-0.6,0.1c-0.2-0.1-0.4-0.3-0.6-0.6c-0.2-0.3-0.3-0.6-0.3-0.8
	c0-0.2,0.1-0.4,0.4-0.5c0.4-0.3,0.9-0.1,1.2,0.6C34.9,41.9,34.9,42.3,34.4,42.6L34.4,42.6z"/>
<path id="Fill-18" sketch:type="MSShapeGroup" fill="#FFFFFF" d="M15.1,5.5c-0.3-0.6-0.7-0.9-1.1-1c-0.4-0.1-0.9,0-1.5,0.3
	C12,5,11.7,5.4,11.6,5.8c-0.1,0.5,0,1,0.3,1.5c0.3,0.6,0.7,0.9,1.2,1c0.4,0.1,0.9,0,1.4-0.3C15,7.8,15.4,7.4,15.5,7
	C15.6,6.5,15.5,6,15.1,5.5L15.1,5.5z M14.1,7.4c-0.4,0.3-0.9,0.1-1.2-0.6c-0.4-0.6-0.3-1.1,0.1-1.4c0.2-0.1,0.4-0.1,0.6-0.1
	C13.8,5.5,14,5.7,14.2,6c0.2,0.3,0.3,0.6,0.3,0.8C14.4,7,14.3,7.2,14.1,7.4L14.1,7.4z"/>
<path id="Fill-19" sketch:type="MSShapeGroup" fill="#FFFFFF" d="M18.8,2.3l-1.3,0.3l-0.2,4l1.1-0.3l0-0.7l1.2-0.3L19.9,6L21,5.7
	L18.8,2.3L18.8,2.3z M18.3,4.8c0-0.6,0-1,0-1.2c0-0.2,0-0.4,0-0.4c0,0.1,0.1,0.2,0.2,0.4c0.1,0.2,0.2,0.4,0.3,0.5l0.3,0.6L18.3,4.8
	L18.3,4.8z"/>
</svg>
