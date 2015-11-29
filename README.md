# React Images

A simple, responsive lightbox component for displaying an array of images.


## Quick start

```jsx
import React from 'react';
import Lightbox from 'react-images';

export default class Sample extends React.Component {
  render() {
    return (
      <Lightbox
      	images={['http://example.com/img1.jpg', 'http://example.com/img2.jpg']}
      	initialImage={0}
      	isOpen={this.props.isOpen}
      	onClose={this.props.onClose}
      	styles={this.props.styles}
      />
    );
  }
}
```


## Demo & Examples

Live demo: [jossmac.github.io/react-images](http://jossmac.github.io/react-images/)

To build the examples locally, run:

```
npm install
npm start
```

Then open [`localhost:8000`](http://localhost:8000) in a browser.

Example using srcset:
```jsx
      <Lightbox
      	images={this.props.images}
      	initialImage={0}
      	isOpen={this.props.isOpen}
      	onClose={this.props.onClose}
      	styles={this.props.styles}
      />

    // images props defined elsewhere in your code
    const IMAGES = [
	{           
	    src: 'http://example.com/example/img1.jpg',
	    srcset: [
			'http://example.com/example/img1_1024.jpg 1024w',
			'http://example.com/example/img1_800.jpg 800w',
			'http://example.com/example/img1_500.jpg 500w',
			'http://example.com/example/img1_320.jpg 320w',
		    ],
	},  
	{           
	    src: 'http://example.com/example/img2.jpg',
	    srcset: [       
			'http://example.com/example/img2_1024.jpg 1024w',
			'http://example.com/example/img2_800.jpg 800w',
			'http://example.com/example/img2_500.jpg 500w',
			'http://example.com/example/img2_320.jpg 320w',
		    ]       
	} 
    ];
 
```

Notes on srcset support:

The srcset attribute is supported by some modern browsers.  Results of browser implementation and behaviour may vary. The sizes attribute uses the default maxWidth CSS property set to the image.  By default this is 80% so 80vw.

Another thing to note is that 'h' or height in the srcset attribute does not yet exist. Because of the nature of the fixed height of a Lightbox this is problematic for portrait sized images.  You will need to calculate what the best 'w' size for a portrait size ought to be given the height of the fixed viewport otherwise unnecessarily large images will be fetched. See issue: [https://github.com/ResponsiveImagesCG/picture-element/issues/86](https://github.com/ResponsiveImagesCG/picture-element/issues/86)

Read more about the srcset and sizes attributes here: [https://ericportis.com/posts/2014/srcset-sizes/](https://ericportis.com/posts/2014/srcset-sizes/).


## Options

<table><thead>
<tr>
<th align="left">Property</th>
<th align="left">Type</th>
<th align="left">Default</th>
<th align="left">Description</th>
</tr>
</thead><tbody>
<tr>
<td align="left">backdropClosesModal</td>
<td align="left">bool</td>
<td align="left">true</td>
<td align="left">Allow users to exit the lightbox by clicking the backdrop</td>
</tr>
<tr>
<td align="left">enableKeyboardInput</td>
<td align="left">bool</td>
<td align="left">true</td>
<td align="left">Supports keyboard input - <code>esc</code>, <code>arrow left</code>, and <code>arrow right</code></td>
</tr>
<tr>
<td align="left">initialImage</td>
<td align="left">number</td>
<td align="left">0</td>
<td align="left">The index of the first image to display</td>
</tr>
<tr>
<td align="left">height</td>
<td align="left">number</td>
<td align="left">600</td>
<td align="left">Maximum height of the carousel; defaults to 600px</td>
</tr>
<tr>
<td align="left">images</td>
<td align="left">array</td>
<td align="left">undefined</td>
<td align="left">An array of objects containing valid src and srcset values of img element</td>
</tr>
<tr>
<td align="left">isOpen</td>
<td align="left">bool</td>
<td align="left">false</td>
<td align="left">Whether or not the lightbox is displayed</td>
</tr>
<tr>
<td align="left">onClose</td>
<td align="left">func</td>
<td align="left">undefined</td>
<td align="left">Handle closing of the lightbox</td>
</tr>
<tr>
<td align="left">showCloseButton</td>
<td align="left">bool</td>
<td align="left">false</td>
<td align="left">Optionally display a close button under the carousel</td>
</tr>
<tr>
<td align="left">width</td>
<td align="left">number</td>
<td align="left">900</td>
<td align="left">Maximum width of the carousel; defaults to 900px</td>
</tr>
</tbody></table>