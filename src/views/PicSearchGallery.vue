<template>
  	<body class=" shell h-100vh w-screen container overflow-y-scroll overflow-x-hidden" style='margin-top: 6em;'>

		<!-- Main -->
		<div id="main" style="z-index:3; ;position:relative; float:right; padding-top:1em;">
			
				<!-- Header -->
					<header id="header">
						<!-- <h1>Lens</h1>
						<p>Just another fine responsive site template by <a href="http://html5up.net">HTML5 UP</a></p>
						<ul class="icons">
							<li><a href="#" class="icon brands fa-twitter"><span class="label">Twitter</span></a></li>
							<li><a href="#" class="icon brands fa-instagram"><span class="label">Instagram</span></a></li>
							<li><a href="#" class="icon brands fa-github"><span class="label">Github</span></a></li>
							<li><a href="#" class="icon fa-envelope"><span class="label">Email</span></a></li>
						</ul> -->

						<PicUploader />
					</header>
					

				<!-- Thumbnail -->
					<section id="thumbnails">
						<h1>留空</h1>
						<!-- <article>
							<a class="thumbnail" href="" data-position="left center"><img src="../assets/thumbs/01.jpg" alt="" /></a>
							<h2>Diam tempus accumsan</h2>
							<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
						</article>
						<article>
							<a class="thumbnail" href="../assets/fulls/02.jpg"><img src="../assets/thumbs/02.jpg" alt="" /></a>
							<h2>Vivamus convallis libero</h2>
							<p>Sed velit lacus, laoreet at venenatis convallis in lorem tincidunt.</p>
						</article>
						<article>
							<a class="thumbnail" href="../assets/fulls/03.jpg" data-position="top center"><img src="../assets/thumbs/03.jpg" alt="" /></a>
							<h2>Nec accumsan enim felis</h2>
							<p>Maecenas eleifend tellus ut turpis eleifend, vitae pretium faucibus.</p>
						</article>
						<article>
							<a class="thumbnail" href="../assets/fulls/04.jpg"><img src="../assets/thumbs/04.jpg" alt="" /></a>
							<h2>Donec maximus nisi eget</h2>
							<p>Tristique in nulla vel congue. Sed sociis natoque parturient nascetur.</p>
						</article>
						<article>
							<a class="thumbnail" href="../assets/fulls/05.jpg" data-position="top center"><img src="../assets/thumbs/05.jpg" alt="" /></a>
							<h2>Nullam vitae nunc vulputate</h2>
							<p>In pellentesque cursus velit id posuere. Donec vehicula nulla.</p>
						</article>
						<article>
							<a class="thumbnail" href="../assets/fulls/06.jpg"><img src="../assets/thumbs/06.jpg" alt="" /></a>
							<h2>Phasellus magna faucibus</h2>
							<p>Nulla dignissim libero maximus tellus varius dictum ut posuere magna.</p>
						</article>
						<article>
							<a class="thumbnail" href="../assets/fulls/07.jpg"><img src="../assets/thumbs/07.jpg" alt="" /></a>
							<h2>Proin quis mauris</h2>
							<p>Etiam ultricies, lorem quis efficitur porttitor, facilisis ante orci urna.</p>
						</article>
						<article>
							<a class="thumbnail" href="../assets/bg01.jpg"><img src="../assets/thumbs/08.jpg" alt="" /></a>
							<h2>Gravida quis varius enim</h2>
							<p>Nunc egestas congue lorem. Nullam dictum placerat ex sapien tortor mattis.</p>
						</article>
						<article>
							<a class="thumbnail" href="../assets/fulls/09.jpg"><img src="../assets/thumbs/09.jpg" alt="" /></a>
							<h2>Morbi eget vitae adipiscing</h2>
							<p>In quis vulputate dui. Maecenas metus elit, dictum praesent lacinia lacus.</p>
						</article>
						<article>
							<a class="thumbnail" href="../assets/fulls/10.jpg"><img src="../assets/thumbs/10.jpg" alt="" /></a>
							<h2>Habitant tristique senectus</h2>
							<p>Vestibulum ante ipsum primis in faucibus orci luctus ac tincidunt dolor.</p>
						</article>
						<article>
							<a class="thumbnail" href="../assets/fulls/11.jpg"><img src="../assets/thumbs/11.jpg" alt="" /></a>
							<h2>Pharetra ex non faucibus</h2>
							<p>Ut sed magna euismod leo laoreet congue. Fusce congue enim ultricies.</p>
						</article>
						<article>
							<a class="thumbnail" href="../assets/fulls/12.jpg"><img src="../assets/thumbs/12.jpg" alt="" /></a>
							<h2>Mattis lorem sodales</h2>
							<p>Feugiat auctor leo massa, nec vestibulum nisl erat faucibus, rutrum nulla.</p>
						</article> -->
					


					</section>
					
					
					<!-- Footer -->
					<!-- <footer id="footer">
						<ul class="copyright">
							<li>&copy; Untitled.</li><li>Design: <a href="http://html5up.net">HTML5 UP</a>.</li>
						</ul>
					</footer> -->
					
				</div>
			<div class="inner-shell" style="width:100%; height: 80vh; margin-top:2vh;">
				<div id="new-viewer" >
				<div class="inner">
					<div class="nav-next"></div>
					<div class="nav-previous"></div>
					<div class="toggle"></div>
				</div>
				<div class="slide active">
					<div class="image" v-bind:class="{'EmptyState': isEmpty}">
						<img :src="srcPic" alt="" style="z-index:3; height:100%; margin:auto;" >
						<div class="caption" v-if="!isEmpty">
							<h2 style="z-index:5; color:white;">Diam tempus accumsan</h2>
							<p style="z-index:5;">Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
						</div>
					</div>
				</div>
				<div class="scroll-x " style="width:calc(100vw - 315px);;height:20vh;">
						
					<div class="pic-container overflow-y-scroll container" style="height:18vh;width: 100%; margin:1em auto; display: flex;flex-wrap: wrap;padding: 5px; overflow-x:scroll;flex-direction:column" >
						<PicContainer
							v-for="(item,index) in picUrlArr" 
							:key="index"
							:nowWidth="item.nowWidth"
							:title="item.title"
							:description="item.description"
							:url="item.url"
							:id="index"
							style="display:flex;flex-grow: 1;margin: 10px;"
							@sendID="changePic"
							>
						</PicContainer>
					</div>
				</div>
			</div>

		</div>

		<!-- Scripts -->
			<!-- <script src="assets/js/jquery.min.js"></script>
			<script src="assets/js/browser.min.js"></script>
			<script src="assets/js/breakpoints.min.js"></script>
			<script src="assets/js/main.js"></script> -->

	</body>
</template>

<script>
import $ from 'jquery'
import jQuery from 'jquery';
import breakpoints from '@/assets/js/breakpoints.min.js'
export default {
    name : 'picSearchGallery',
	components: {
		PicContainer: () => import('@/components/PicContainer.vue'),
		PicUploader: () => import('@/components/PicUploader.vue'),
	},
	data() {
		return {
		picUrlArr: [
			{url:'@/assets/bg01.jpg', title:'1', description:'1', originalWidth:NaN, nowWidth:NaN},
			{url:'@/assets/bg02.jpg', title:'1', description:'1', originalWidth:NaN, nowWidth:NaN},
			{url:'@/assets/bg03.jpg', title:'1', description:'1', originalWidth:NaN, nowWidth:NaN},
			{url:'@/assets/logo.png', title:'1', description:'2', originalWidth:NaN, nowWidth:NaN},
			{url:'@/assets/bg1.png', title:'1', description:'2', originalWidth:NaN, nowWidth:NaN},
			{url:'@/assets/bg2.png', title:'1', description:'1', originalWidth:NaN, nowWidth:NaN},
			{url:'@/assets/bg3.png', title:'1', description:'1', originalWidth:NaN, nowWidth:NaN},
			{url:'@/assets/bg01.jpg', title:'1', description:'1', originalWidth:NaN, nowWidth:NaN},
			{url:'@/assets/bg02.jpg', title:'1', description:'1', originalWidth:NaN, nowWidth:NaN},
			{url:'@/assets/bg03.jpg', title:'1', description:'1', originalWidth:NaN, nowWidth:NaN},
			{url:'@/assets/logo.png', title:'1', description:'2', originalWidth:NaN, nowWidth:NaN},
			{url:'@/assets/bg1.png', title:'1', description:'2', originalWidth:NaN, nowWidth:NaN},
			{url:'@/assets/bg2.png', title:'1', description:'1', originalWidth:NaN, nowWidth:NaN},
			{url:'@/assets/bg3.png', title:'1', description:'1', originalWidth:NaN, nowWidth:NaN},
		],
		referHight: 140,  // refer height for each pic in const height waterfall layout
		srcPic: '',
		isEmpty: true,
		}
	},
	
	methods: {
    getPicUrl() {
      axios.get('http://localhost:8080/picUrl').then((res) => {
        console.log(res.data);
        this.picUrlArr = res.data;
      });
    },

    // read all url in picUrlArr and record their originalWidth
    getPicWidth() {
      for (let i = 0; i < this.picUrlArr.length; i++) {
        const img = new Image();
        img.src = require('@/assets/'+this.picUrlArr[i].url.slice(9, this.picUrlArr[i].url.length));
        img.onload = () => {
          this.picUrlArr[i].originalWidth = img.width;
          // this.picUrlArr[i].nowWidth = img.width;
          console.log(i, img.width)
        };
      }
      console.log('read width done')
    },

    //scale the image to reference height
    scalePic() {
      for (let i = 0; i < this.picUrlArr.length; i++) {
        this.picUrlArr[i].nowWidth = this.picUrlArr[i].originalWidth * this.referHight / this.picUrlArr[i].originalHeight;
      }
      console.log('scaled:')
      console.log(this.picUrlArr  )
    },

    changeList() {
      // getPicUrl();
      this.getPicWidth();
      this.scalePic();
    //   this.isListAnswer = !this.isListAnswer;
    },
	changePic(id) {
		console.log(id)

        this.srcPic = require('@/assets/'+this.picUrlArr[id].url.slice(9, this.picUrlArr[id].url.length));
		// this.srcPic = this.picUrlArr[id].url
	}
  },
  created() {
	// this.getPicUrl();
	this.getPicWidth();
	this.scalePic();
	// if picUrlArr is empty, isEmpty is true
	if (this.picUrlArr.length == 0) {
		this.isEmpty = true;
	} else {
		this.isEmpty = false;
		this.srcPic= require('@/assets/'+this.picUrlArr[0].url.slice(9, this.picUrlArr[0].url.length));
	}
  },
}
</script>

<style scoped >
@import url(fontawesome-all.min.css);
@import url("https://fonts.googleapis.com/css?family=Roboto:400,700");

/*
	Lens by HTML5 UP
	html5up.net | @ajlkn
	Free for personal and commercial use under the CCA 3.0 license (html5up.net/license)
*/

.image {
background-position: left center; 
width:calc(100vw - 315px); 
height: 75vh; position: relative; 
overflow:hidden; 
background-color:#f5f4f3; border-radius: 8px;
}
.caption {
	position: absolute; bottom:-20vh; left: 0; z-index:4; color:black; ; width:100%; height:20vh;
/* background:linear-gradient(to top,rgba(0,0,0.8) , rgba(0,0,0,0.1)); */
	background:linear-gradient(to top, rgba(0, 0, 0, 0.8), transparent);
	color:white;
	/* background:hsla(0,0%,100%,.3); */
	padding: 2em 3em;
	transition: 0.55s;
    transition-delay: 0.3s;

}

.image, .EmptyState {

}

.caption:before{
  content:'';
  position:absolute;
  left: 0;bottom: 0;
  filter:blur(60px);
  background: rgb(32, 30, 30) fixed;
  width: 100%;
  height:100%;
  /* background-image:linear-gradient(90deg,#fb3 11px,transparent 0),
  linear-gradient(90deg,#ab4 23px,transparent 0),
  linear-gradient(90deg,#655 41px,transparent 0);
  background-size: 41px 100%,61px 100%,83px 100%; */

  /* background:linear-gradient(to top,rgba(0,0,0.6) , rgba(0,0,0,0.1)); */
  z-index:-1;
}

.image:hover .caption{
	transform: translate(0%, -100%);
	transition-duration: 0.2s;
    transition-delay: 0;
}
.EmptyState {
  background:
      linear-gradient(217deg, rgba(255,0,0,.5), rgba(255,0,0,0) 70.71%),
      linear-gradient(127deg, rgba(0,255,0,.5), rgba(0,255,0,0) 70.71%),
      linear-gradient(336deg, rgba(0,0,255,.5), rgba(0,0,255,0) 70.71%);
    border-radius: 8px;
}
/* .image:hover .caption::before{
	transform: translate(0%, 100%);
	transition-duration: 0.2s;
} */

html, body, div, span, applet, object,
iframe, h1, h2, h3, h4, h5, h6, p, blockquote,
pre, a, abbr, acronym, address, big, cite,
code, del, dfn, em, img, ins, kbd, q, s, samp,
small, strike, strong, sub, sup, tt, var, b,
u, i, center, dl, dt, dd, ol, ul, li, fieldset,
form, label, legend, table, caption, tbody,
tfoot, thead, tr, th, td, article, aside,
canvas, details, embed, figure, figcaption,
footer, header, hgroup, menu, nav, output, ruby,
section, summary, time, mark, audio, video {
	margin: 0;
	padding: 0;
	border: 0;
	font-size: 100%;
	font: inherit;
	vertical-align: baseline;}


*::-webkit-scrollbar {
    display: none;
}

/* Hide scrollbar for IE, Edge and Firefox */
*{
    -ms-overflow-style: none;  /* IE and Edge */
    scrollbar-width: none;  /* Firefox */
}

article, aside, details, figcaption, figure,
footer, header, hgroup, menu, nav, section {
	display: block;}

body {
	line-height: 1;
}

ol, ul {
	list-style: none;
}

blockquote, q {
	quotes: none;
}

	blockquote:before, blockquote:after, q:before, q:after {
		content: '';
		content: none;
	}

table {
	border-collapse: collapse;
	border-spacing: 0;
}

body {
	-webkit-text-size-adjust: none;
}

mark {
	background-color: transparent;
	color: inherit;
}

input::-moz-focus-inner {
	border: 0;
	padding: 0;
}

input, select, textarea {
	-moz-appearance: none;
	-webkit-appearance: none;
	-ms-appearance: none;
	appearance: none;
}

/* Basic */

	/*
			@-ms-viewport {
				width: device-width;
			}
		*/

	@media screen and (max-width: 480px) {

		html, body {
			min-width: 320px;
		}

	}

	body.is-preload-0 *, body.is-preload-0 *:before, body.is-preload-0 *:after {
		-moz-animation: none !important;
		-webkit-animation: none !important;
		-ms-animation: none !important;
		animation: none !important;
		-moz-transition: none !important;
		-webkit-transition: none !important;
		-ms-transition: none !important;
		transition: none !important;
	}

	html {
		box-sizing: border-box;
	}

	*, *:before, *:after {
		box-sizing: inherit;
	}

	html, body {
		background-color: #101010;
		overflow: hidden;
	}

/* Type */

	html {
		font-size: 16pt;
	}

		@media screen and (max-width: 1680px) {

			html {
				font-size: 12pt;
			}

		}

		@media screen and (max-width: 1280px) {

			html {
				font-size: 11pt;
			}

		}

	body {
		background-color: #fff;
		color: #aaa;
	}

	body, input, select, textarea {
		font-family: "Roboto", Helvetica, sans-serif;
		font-weight: 400;
		line-height: 1.65;
		font-size: 1em;
		color: #aaa;
	}

	a {
		-moz-transition: color 0.25s ease, border-bottom-color 0.25s ease;
		-webkit-transition: color 0.25s ease, border-bottom-color 0.25s ease;
		-ms-transition: color 0.25s ease, border-bottom-color 0.25s ease;
		transition: color 0.25s ease, border-bottom-color 0.25s ease;
		border-bottom: dotted 1px;
		color: inherit;
		text-decoration: none;
	}

		a:hover {
			border-bottom-color: transparent;
			color: #00D3B7;
		}

	strong, b {
		font-weight: 400;
		color: #555;
	}

	em, i {
		font-style: italic;
	}

	p {
		margin: 0 0 1.25em 0;
	}

	h1, h2, h3, h4, h5, h6 {
		font-weight: 400;
		line-height: 1.25;
		margin: 0 0 0.5em 0;
		color: #555;
	}

		h1 a, h2 a, h3 a, h4 a, h5 a, h6 a {
			color: inherit;
			text-decoration: none;
		}

	h2 {
		font-size: 1.25em;
	}

	h3 {
		font-size: 1em;
	}

	h4 {
		font-size: 0.9em;
	}

	h5 {
		font-size: 0.8em;
	}

	h6 {
		font-size: 0.7em;
	}

	sub {
		font-size: 0.8em;
		position: relative;
		top: 0.5em;
	}

	sup {
		font-size: 0.8em;
		position: relative;
		top: -0.5em;
	}

	blockquote {
		border-left: solid 4px #ccc;
		font-style: italic;
		margin: 0 0 1.25em 0;
		padding: 0.3125em 0 0.3125em 1.25em;
	}

	code {
		border-radius: 4px;
		border: solid 1px;
		font-family: "Courier New", monospace;
		font-size: 0.9em;
		margin: 0 0.25em;
		padding: 0.25em 0.65em;
		border-color: #ccc;
	}

	pre {
		-webkit-overflow-scrolling: touch;
		font-family: "Courier New", monospace;
		font-size: 0.9em;
		margin: 0 0 1.25em 0;
	}

		pre code {
			display: block;
			padding: 1em 1.5em;
			overflow-x: auto;
		}

	hr {
		border: 0;
		border-bottom: solid 1px #ccc;
		margin: 1.25em 0;
	}

		hr.major {
			margin: 1.875em 0;
		}

	.align-left {
		text-align: left;
	}

	.align-center {
		text-align: center;
	}

	.align-right {
		text-align: right;
	}

/* Button */

	input[type="submit"],
	input[type="reset"],
	input[type="button"],
	button,
	.button {
		-moz-appearance: none;
		-webkit-appearance: none;
		-ms-appearance: none;
		appearance: none;
		-moz-transition: background-color 0.25s ease-in-out, border-color 0.25s ease-in-out, color 0.25s ease-in-out;
		-webkit-transition: background-color 0.25s ease-in-out, border-color 0.25s ease-in-out, color 0.25s ease-in-out;
		-ms-transition: background-color 0.25s ease-in-out, border-color 0.25s ease-in-out, color 0.25s ease-in-out;
		transition: background-color 0.25s ease-in-out, border-color 0.25s ease-in-out, color 0.25s ease-in-out;
		background-color: transparent;
		border-radius: 4px;
		border: solid 1px #ccc;
		color: #555;
		cursor: pointer;
		display: inline-block;
		line-height: 1;
		padding: 0.75em 1.5em;
		text-align: center;
		text-decoration: none;
		white-space: nowrap;
	}

		input[type="submit"]:hover,
		input[type="reset"]:hover,
		input[type="button"]:hover,
		button:hover,
		.button:hover {
			border-color: #00D3B7;
			color: #00D3B7;
		}

			input[type="submit"]:hover:active,
			input[type="reset"]:hover:active,
			input[type="button"]:hover:active,
			button:hover:active,
			.button:hover:active {
				background-color: rgba(0, 211, 183, 0.15);
			}

		input[type="submit"].icon,
		input[type="reset"].icon,
		input[type="button"].icon,
		button.icon,
		.button.icon {
			padding-left: 1.35em;
		}

			input[type="submit"].icon:before,
			input[type="reset"].icon:before,
			input[type="button"].icon:before,
			button.icon:before,
			.button.icon:before {
				margin-right: 0.5em;
			}

		input[type="submit"].fit,
		input[type="reset"].fit,
		input[type="button"].fit,
		button.fit,
		.button.fit {
			width: 100%;
		}

		input[type="submit"].small,
		input[type="reset"].small,
		input[type="button"].small,
		button.small,
		.button.small {
			font-size: 0.8em;
		}

		input[type="submit"].large,
		input[type="reset"].large,
		input[type="button"].large,
		button.large,
		.button.large {
			font-size: 1.35em;
		}

		input[type="submit"].disabled, input[type="submit"]:disabled,
		input[type="reset"].disabled,
		input[type="reset"]:disabled,
		input[type="button"].disabled,
		input[type="button"]:disabled,
		button.disabled,
		button:disabled,
		.button.disabled,
		.button:disabled {
			pointer-events: none;
			opacity: 0.25;
		}

/* Form */

	form {
		margin: 0 0 1.25em 0;
	}

	label {
		color: #555;
		display: block;
		font-size: 0.9em;
		font-weight: 400;
		margin: 0 0 0.625em 0;
	}

	input[type="text"],
	input[type="password"],
	input[type="email"],
	select,
	textarea {
		-moz-appearance: none;
		-webkit-appearance: none;
		-ms-appearance: none;
		appearance: none;
		background-color: transparent;
		border-radius: 4px;
		border: solid 1px #ccc;
		color: inherit;
		display: block;
		outline: 0;
		padding: 0 0.75em;
		text-decoration: none;
		width: 100%;
	}

		input[type="text"]:invalid,
		input[type="password"]:invalid,
		input[type="email"]:invalid,
		select:invalid,
		textarea:invalid {
			box-shadow: none;
		}

		input[type="text"]:focus,
		input[type="password"]:focus,
		input[type="email"]:focus,
		select:focus,
		textarea:focus {
			border-color: #00D3B7;
		}

	select {
		/* background-image: url("data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' width='40' height='40' preserveAspectRatio='none' viewBox='0 0 40 40'%3E%3Cpath d='M9.4,12.3l10.4,10.4l10.4-10.4c0.2-0.2,0.5-0.4,0.9-0.4c0.3,0,0.6,0.1,0.9,0.4l3.3,3.3c0.2,0.2,0.4,0.5,0.4,0.9 c0,0.4-0.1,0.6-0.4,0.9L20.7,31.9c-0.2,0.2-0.5,0.4-0.9,0.4c-0.3,0-0.6-0.1-0.9-0.4L4.3,17.3c-0.2-0.2-0.4-0.5-0.4-0.9 c0-0.4,0.1-0.6,0.4-0.9l3.3-3.3c0.2-0.2,0.5-0.4,0.9-0.4S9.1,12.1,9.4,12.3z' fill='%23ccc' /%3E%3C/svg%3E"); */
		background-size: 1.25rem;
		background-repeat: no-repeat;
		background-position: calc(100% - 1rem) center;
		height: 2.75em;
		padding-right: 2.75em;
		text-overflow: ellipsis;
	}

		select option {
			color: #555;
			background: #fff;
		}

		select:focus::-ms-value {
			background-color: transparent;
		}

		select::-ms-expand {
			display: none;
		}

	.select-wrapper {
		text-decoration: none;
		display: block;
		position: relative;
	}

		.select-wrapper:before {
			-moz-osx-font-smoothing: grayscale;
			-webkit-font-smoothing: antialiased;
			display: inline-block;
			font-style: normal;
			font-variant: normal;
			text-rendering: auto;
			line-height: 1;
			text-transform: none !important;
			font-family: 'Font Awesome 5 Free';
			font-weight: 900;
		}

		.select-wrapper:before {
			color: #ccc;
			content: '\f107';
			display: block;
			height: 2.75em;
			line-height: 2.75em;
			pointer-events: none;
			position: absolute;
			right: 0;
			text-align: center;
			top: 0;
			width: 2.75em;
		}

		.select-wrapper select::-ms-expand {
			display: none;
		}

	input[type="text"],
	input[type="password"],
	input[type="email"],
	select {
		height: 2.75em;
	}

	textarea {
		padding: 0.75em 1em;
	}

	input[type="checkbox"],
	input[type="radio"] {
		-moz-appearance: none;
		-webkit-appearance: none;
		-ms-appearance: none;
		appearance: none;
		display: block;
		float: left;
		margin-right: -2em;
		opacity: 0;
		width: 1em;
		z-index: -1;
	}

		input[type="checkbox"] + label,
		input[type="radio"] + label {
			text-decoration: none;
			color: #aaa;
			cursor: pointer;
			display: inline-block;
			font-size: 1em;
			font-weight: 400;
			margin: 0;
			padding-left: 2.4em;
			padding-right: 0.75em;
			position: relative;
		}

			input[type="checkbox"] + label:before,
			input[type="radio"] + label:before {
				-moz-osx-font-smoothing: grayscale;
				-webkit-font-smoothing: antialiased;
				display: inline-block;
				font-style: normal;
				font-variant: normal;
				text-rendering: auto;
				line-height: 1;
				text-transform: none !important;
				font-family: 'Font Awesome 5 Free';
				font-weight: 900;
			}

			input[type="checkbox"] + label:before,
			input[type="radio"] + label:before {
				background: transparent;
				border-radius: 4px;
				border: solid 1px #ccc;
				content: '';
				display: inline-block;
				font-size: 0.8em;
				height: 2.0625em;
				left: 0;
				line-height: 2.0625em;
				position: absolute;
				text-align: center;
				top: 0;
				width: 2.0625em;
			}

		input[type="checkbox"]:checked + label:before,
		input[type="radio"]:checked + label:before {
			background-color: #555;
			border-color: #555;
			color: #fff;
			content: '\f00c';
		}

		input[type="checkbox"]:focus + label:before,
		input[type="radio"]:focus + label:before {
			border-color: #00D3B7;
		}

	input[type="checkbox"] + label:before {
		border-radius: 4px;
	}

	input[type="radio"] + label:before {
		border-radius: 100%;
	}

	::-webkit-input-placeholder {
		opacity: 1.0;
		color: #ccc !important;
	}

	:-moz-placeholder {
		opacity: 1.0;
		color: #ccc !important;
	}

	::-moz-placeholder {
		opacity: 1.0;
		color: #ccc !important;
	}

	:-ms-input-placeholder {
		opacity: 1.0;
		color: #ccc !important;
	}

	.field {
		margin: 0 0 1.25em 0;
	}

/* Icon */

	.icon {
		text-decoration: none;
		border-bottom: none;
		position: relative;
	}

		.icon:before {
			-moz-osx-font-smoothing: grayscale;
			-webkit-font-smoothing: antialiased;
			display: inline-block;
			font-style: normal;
			font-variant: normal;
			text-rendering: auto;
			line-height: 1;
			text-transform: none !important;
			font-family: 'Font Awesome 5 Free';
			font-weight: 400;
		}

		.icon > .label {
			display: none;
		}

		.icon:before {
			line-height: inherit;
		}

		.icon.solid:before {
			font-weight: 900;
		}

		.icon.brands:before {
			font-family: 'Font Awesome 5 Brands';
		}

/* List */

	ol {
		list-style: decimal;
		margin: 0 0 1.25em 0;
		padding-left: 1.25em;
	}

		ol li {
			padding-left: 0.25em;
		}

	ul {
		list-style: disc;
		margin: 0 0 1.25em 0;
		padding-left: 1em;
	}

		ul li {
			padding-left: 0.5em;
		}

		ul.alt {
			list-style: none;
			padding-left: 0;
		}

			ul.alt li {
				border-top: solid 1px #ccc;
				padding: 0.5em 0;
			}

				ul.alt li:first-child {
					border-top: 0;
					padding-top: 0;
				}

	dl {
		margin: 0 0 1.25em 0;
	}

		dl dt {
			display: block;
			font-weight: 400;
			margin: 0 0 0.625em 0;
		}

		dl dd {
			margin-left: 1.25em;
		}

/* Actions */

	ul.actions {
		display: -moz-flex;
		display: -webkit-flex;
		display: -ms-flex;
		display: flex;
		cursor: default;
		list-style: none;
		margin-left: -0.625em;
		padding-left: 0;
	}

		ul.actions li {
			padding: 0 0 0 0.625em;
			vertical-align: middle;
		}

		ul.actions.special {
			-moz-justify-content: center;
			-webkit-justify-content: center;
			-ms-justify-content: center;
			justify-content: center;
			width: 100%;
			margin-left: 0;
		}

			ul.actions.special li:first-child {
				padding-left: 0;
			}

		ul.actions.stacked {
			-moz-flex-direction: column;
			-webkit-flex-direction: column;
			-ms-flex-direction: column;
			flex-direction: column;
			margin-left: 0;
		}

			ul.actions.stacked li {
				padding: 0.8125em 0 0 0;
			}

				ul.actions.stacked li:first-child {
					padding-top: 0;
				}

		ul.actions.fit {
			width: calc(100% + 0.625em);
		}

			ul.actions.fit li {
				-moz-flex-grow: 1;
				-webkit-flex-grow: 1;
				-ms-flex-grow: 1;
				flex-grow: 1;
				-moz-flex-shrink: 1;
				-webkit-flex-shrink: 1;
				-ms-flex-shrink: 1;
				flex-shrink: 1;
				width: 100%;
			}

				ul.actions.fit li > * {
					width: 100%;
				}

			ul.actions.fit.stacked {
				width: 100%;
			}

		@media screen and (max-width: 480px) {

			ul.actions:not(.fixed) {
				-moz-flex-direction: column;
				-webkit-flex-direction: column;
				-ms-flex-direction: column;
				flex-direction: column;
				margin-left: 0;
				width: 100% !important;
			}

				ul.actions:not(.fixed) li {
					-moz-flex-grow: 1;
					-webkit-flex-grow: 1;
					-ms-flex-grow: 1;
					flex-grow: 1;
					-moz-flex-shrink: 1;
					-webkit-flex-shrink: 1;
					-ms-flex-shrink: 1;
					flex-shrink: 1;
					padding: 0.625em 0 0 0;
					text-align: center;
					width: 100%;
				}

					ul.actions:not(.fixed) li > * {
						width: 100%;
					}

					ul.actions:not(.fixed) li:first-child {
						padding-top: 0;
					}

					ul.actions:not(.fixed) li input[type="submit"],
					ul.actions:not(.fixed) li input[type="reset"],
					ul.actions:not(.fixed) li input[type="button"],
					ul.actions:not(.fixed) li button,
					ul.actions:not(.fixed) li .button {
						width: 100%;
					}

						ul.actions:not(.fixed) li input[type="submit"].icon:before,
						ul.actions:not(.fixed) li input[type="reset"].icon:before,
						ul.actions:not(.fixed) li input[type="button"].icon:before,
						ul.actions:not(.fixed) li button.icon:before,
						ul.actions:not(.fixed) li .button.icon:before {
							margin-left: -0.5rem;
						}

		}

/* Icons */

	ul.icons {
		cursor: default;
		list-style: none;
		padding-left: 0;
	}

		ul.icons li {
			display: inline-block;
			padding: 0 1em 0 0;
		}

			ul.icons li:last-child {
				padding-right: 0;
			}

			ul.icons li .icon:before {
				font-size: 1.5rem;
			}

/* Main */

	#main {
		-moz-transition: opacity 0.75s ease, right 0.75s ease, left 0.75s ease, visibility 0.75s;
		-webkit-transition: opacity 0.75s ease, right 0.75s ease, left 0.75s ease, visibility 0.75s;
		-ms-transition: opacity 0.75s ease, right 0.75s ease, left 0.75s ease, visibility 0.75s;
		transition: opacity 0.75s ease, right 0.75s ease, left 0.75s ease, visibility 0.75s;
		-webkit-overflow-scrolling: touch;
		position: fixed;
		top: 0;
		width: 22.5em;
		height: 100%;
		background: #fff;
		outline: 0;
		overflow-x: hidden;
		overflow-y: auto;
		text-align: right;
		visibility: visible;
		z-index: 10000;
		right: 0;
	}

		#main .toggle {
			-webkit-tap-highlight-color: rgba(0, 0, 0, 0);
			position: absolute;
			top: 0;
			width: 4em;
			height: 4em;
			/* background-image: url("images/close-small-alt.svg"); */
			background-repeat: no-repeat;
			background-size: 32px 32px;
			cursor: pointer;
			display: none;
			z-index: 1;
			background-position: 0.5em 0.5em;
			left: 0;
		}

		body.fullscreen #main {
			visibility: hidden;
			right: -22.5em;
		}

		body.is-preload-1 #main {
			opacity: 0;
			right: -2em;
		}

		@media screen and (max-width: 1280px) {

			#main {
				width: 19em;
			}

				body.fullscreen #main {
					right: -19em;
				}

		}

		@media screen and (max-width: 980px) {

			#main {
				background: rgba(255, 255, 255, 0.925);
			}

				#main .toggle {
					display: block;
				}

		}

		@media screen and (max-width: 480px) {

			#main {
				-moz-transition: opacity 0.5s ease, visibility 0.5s;
				-webkit-transition: opacity 0.5s ease, visibility 0.5s;
				-ms-transition: opacity 0.5s ease, visibility 0.5s;
				transition: opacity 0.5s ease, visibility 0.5s;
				width: 100%;
				background: #fff;
				text-align: center;
			}

				body.is-preload-1 #main {
					left: auto !important;
					right: auto !important;
				}

				body.fullscreen #main {
					left: auto !important;
					right: auto !important;
					opacity: 0;
				}

				#main .toggle {
					display: none;
				}

		}

/* Header */

	#header {
		padding: 3em 2.25em 1.75em 2.25em ;
	}

		#header h1 {
			font-size: 2.25em;
			font-weight: 700;
		}

/* Footer */

	#footer {
		padding: 2.25em 2.25em 1em 2.25em ;
	}

		#footer .copyright {
			list-style: none;
			padding: 0;
		}

			#footer .copyright li {
				display: inline-block;
				font-size: 0.8em;
				margin-left: 0.35em;
				padding: 0;
			}

				#footer .copyright li:first-child {
					margin-left: 0;
				}

/* Thumbnails */

	#thumbnails {
		display: -moz-flex;
		display: -webkit-flex;
		display: -ms-flex;
		display: flex;
		-moz-flex-wrap: wrap;
		-webkit-flex-wrap: wrap;
		-ms-flex-wrap: wrap;
		flex-wrap: wrap;
		padding: 0 0.75em;
	}

		#thumbnails article {
			position: relative;
			width: 50%;
			background: #101010;
			outline: 0;
		}

			#thumbnails article .thumbnail {
				-webkit-tap-highlight-color: rgba(0, 0, 0, 0);
				display: block;
				position: relative;
				border: 0;
				outline: 0;
			}

				#thumbnails article .thumbnail img {
					display: block;
					width: 100%;
				}

				#thumbnails article .thumbnail:before {
					pointer-events: none;
					-moz-transition: opacity 0.25s ease;
					-webkit-transition: opacity 0.25s ease;
					-ms-transition: opacity 0.25s ease;
					transition: opacity 0.25s ease;
					content: '';
					position: absolute;
					left: 0;
					top: 0;
					width: 100%;
					height: 100%;
					box-shadow: inset 0 0 0 2px #00D3B7, inset 0 0 0px 3px rgba(0, 0, 0, 0.15);
					opacity: 0;
					z-index: 1;
				}

				#thumbnails article .thumbnail:focus:before {
					opacity: 0.5;
				}

			#thumbnails article h2, #thumbnails article p {
				display: none;
			}

			#thumbnails article.active .thumbnail:before {
				opacity: 1;
			}

		@media screen and (max-width: 480px) {

			#thumbnails article .thumbnail:before {
				display: none;
			}

		}

/* Viewer */

	@-moz-keyframes spinner {
		0% {
			-moz-transform: rotate(0deg);
			-webkit-transform: rotate(0deg);
			-ms-transform: rotate(0deg);
			transform: rotate(0deg);
		}

		100% {
			-moz-transform: rotate(360deg);
			-webkit-transform: rotate(360deg);
			-ms-transform: rotate(360deg);
			transform: rotate(360deg);
		}
	}

	@-webkit-keyframes spinner {
		0% {
			-moz-transform: rotate(0deg);
			-webkit-transform: rotate(0deg);
			-ms-transform: rotate(0deg);
			transform: rotate(0deg);
		}

		100% {
			-moz-transform: rotate(360deg);
			-webkit-transform: rotate(360deg);
			-ms-transform: rotate(360deg);
			transform: rotate(360deg);
		}
	}

	@-ms-keyframes spinner {
		0% {
			-moz-transform: rotate(0deg);
			-webkit-transform: rotate(0deg);
			-ms-transform: rotate(0deg);
			transform: rotate(0deg);
		}

		100% {
			-moz-transform: rotate(360deg);
			-webkit-transform: rotate(360deg);
			-ms-transform: rotate(360deg);
			transform: rotate(360deg);
		}
	}

	@keyframes spinner {
		0% {
			-moz-transform: rotate(0deg);
			-webkit-transform: rotate(0deg);
			-ms-transform: rotate(0deg);
			transform: rotate(0deg);
		}

		100% {
			-moz-transform: rotate(360deg);
			-webkit-transform: rotate(360deg);
			-ms-transform: rotate(360deg);
			transform: rotate(360deg);
		}
	}

	#viewer {
		/* -moz-transition: opacity 0.75s ease, width 0.75s ease;
		-webkit-transition: opacity 0.75s ease, width 0.75s ease;
		-ms-transition: opacity 0.75s ease, width 0.75s ease;
		transition: opacity 0.75s ease, width 0.75s ease; */
		position: absolute;
		top: 0;
		width: calc(100% - 22.5em);
		height: 100%;
		left: 0;
	}

		#viewer .inner {
			pointer-events: none;
			position: absolute;
			top: 0;
			left: 0;
			width: 100%;
			height: 100%;
			z-index: 3;
		}

			#viewer .inner > * {
				pointer-events: auto;
			}

			#viewer .inner:before {
				background-image: -moz-linear-gradient(left, rgba(16,16,16,0.2), rgba(16,16,16,0) 10em, rgba(16,16,16,0)), -moz-linear-gradient(right, rgba(16,16,16,0.2), rgba(16,16,16,0) 10em, rgba(16,16,16,0));
				background-image: -webkit-linear-gradient(left, rgba(16,16,16,0.2), rgba(16,16,16,0) 10em, rgba(16,16,16,0)), -webkit-linear-gradient(right, rgba(16,16,16,0.2), rgba(16,16,16,0) 10em, rgba(16,16,16,0));
				background-image: -ms-linear-gradient(left, rgba(16,16,16,0.2), rgba(16,16,16,0) 10em, rgba(16,16,16,0)), -ms-linear-gradient(right, rgba(16,16,16,0.2), rgba(16,16,16,0) 10em, rgba(16,16,16,0));
				background-image: linear-gradient(left, rgba(16,16,16,0.2), rgba(16,16,16,0) 10em, rgba(16,16,16,0)), linear-gradient(right, rgba(16,16,16,0.2), rgba(16,16,16,0) 10em, rgba(16,16,16,0));
				content: '';
				display: block;
				position: absolute;
				top: 0;
				left: 0;
				width: 100%;
				height: 100%;
			}

			#viewer .inner .toggle {
				-webkit-tap-highlight-color: rgba(0, 0, 0, 0);
				position: absolute;
				top: 0;
				width: 4em;
				height: 4em;
				/* background-image: url("images/close.svg"); */
				background-repeat: no-repeat;
				background-size: 64px 64px;
				cursor: pointer;
				z-index: 3;
				right: 0;
				background-position: calc(100% - 0.75em) 0.75em;
			}

			#viewer .inner .nav-next,
			#viewer .inner .nav-previous {
				-webkit-tap-highlight-color: rgba(0, 0, 0, 0);
				position: absolute;
				top: 50%;
				width: 6em;
				height: 6em;
				margin-top: -3em;
				/* background-image: url("images/arrow.svg"); */
				background-position: center;
				background-repeat: no-repeat;
				background-size: contain;
				cursor: pointer;
			}

			#viewer .inner .nav-previous {
				-moz-transform: scaleX(-1);
				-webkit-transform: scaleX(-1);
				-ms-transform: scaleX(-1);
				transform: scaleX(-1);
				left: 0;
			}

			#viewer .inner .nav-next {
				right: 0;
			}

		#viewer .slide {
			-moz-transition: opacity 0.5s ease-in-out;
			-webkit-transition: opacity 0.5s ease-in-out;
			-ms-transition: opacity 0.5s ease-in-out;
			transition: opacity 0.5s ease-in-out;
			position: absolute;
			top: 0;
			left: 0;
			width: 100%;
			height: 100%;
			opacity: 1;
			z-index: 3;
		}

			#viewer .slide .caption {
				background-image: -moz-linear-gradient(bottom, rgba(16,16,16,0.75), rgba(16,16,16,0.25) 80%, rgba(16,16,16,0));
				background-image: -webkit-linear-gradient(bottom, rgba(16,16,16,0.75), rgba(16,16,16,0.25) 80%, rgba(16,16,16,0));
				background-image: -ms-linear-gradient(bottom, rgba(16,16,16,0.75), rgba(16,16,16,0.25) 80%, rgba(16,16,16,0));
				background-image: linear-gradient(bottom, rgba(16,16,16,0.75), rgba(16,16,16,0.25) 80%, rgba(16,16,16,0));
				padding: 2em 2em 0.75em 2em ;
				position: absolute;
				bottom: 0;
				left: 0;
				width: 100%;
				color: rgba(255, 255, 255, 0.5);
				z-index: 3;
			}

				#viewer .slide .caption h2, #viewer .slide .caption h3, #viewer .slide .caption h4, #viewer .slide .caption h5, #viewer .slide .caption h6 {
					color: #fff;
				}

			#viewer .slide .image {
				/* -moz-transition: opacity 0.5s ease-in-out;
				-webkit-transition: opacity 0.5s ease-in-out;
				-ms-transition: opacity 0.5s ease-in-out;
				transition: opacity 0.5s ease-in-out; */
				position: absolute;
				top: 0;
				left: 0;
				width: 100%;
				height: 100%;
				background-repeat: no-repeat;
				background-size: cover;
				/* opacity: 0; */
			}

			#viewer .slide:before {
				-moz-animation: spinner 1s linear infinite;
				-webkit-animation: spinner 1s linear infinite;
				-ms-animation: spinner 1s linear infinite;
				animation: spinner 1s linear infinite;
				-moz-transition: opacity 0.5s ease-in-out;
				-webkit-transition: opacity 0.5s ease-in-out;
				-ms-transition: opacity 0.5s ease-in-out;
				transition: opacity 0.5s ease-in-out;
				content: '';
				display: block;
				position: absolute;
				top: 50%;
				left: 50%;
				width: 3em;
				height: 3em;
				/* background-image: url("images/spinner.svg"); */
				background-position: center;
				background-repeat: no-repeat;
				background-size: contain;
				margin: -1.5em 0 0 -1.5em;
				opacity: 0;
			}

			#viewer .slide.loading:before {
				opacity: 1;
			}

			#viewer .slide.active .image {
				opacity: 1;
			}

		body.fullscreen #viewer {
			width: 100%;
		}

			body.fullscreen #viewer .inner .toggle {
				/* background-image: url("images/open.svg"); */
			}

		/* body.is-preload-1 #viewer {
			opacity: 0;
		}

		body.is-preload-2 #viewer .slide {
			opacity: 0;
		} */

		@media screen and (max-width: 1280px) {

			#viewer {
				width: calc(100% - 19em);
			}

		}

		@media screen and (max-width: 980px) {

			#viewer {
				width: 100%;
			}

				#viewer .inner .toggle {
					-moz-transition: opacity 0.75s ease;
					-webkit-transition: opacity 0.75s ease;
					-ms-transition: opacity 0.75s ease;
					transition: opacity 0.75s ease;
					/* background-image: url("images/open.svg"); */
					opacity: 0;
					right: 0;
				}

				body.fullscreen #viewer .inner .toggle {
					opacity: 1;
				}

		}

		@media screen and (max-width: 736px) {

			#viewer .inner .toggle {
				background-size: 32px 32px;
			}

			#viewer .inner .nav-next,
			#viewer .inner .nav-previous {
				/* background-image: url("images/arrow-small.svg"); */
				background-size: 32px 32px;
			}

			body.fullscreen #viewer .inner .toggle {
				/* background-image: url("images/open-small.svg"); */
			}

		}

		@media screen and (max-width: 480px) {

			#viewer {
				-moz-transition: opacity 0.5s ease;
				-webkit-transition: opacity 0.5s ease;
				-ms-transition: opacity 0.5s ease;
				transition: opacity 0.5s ease;
				-moz-transition-delay: 0s;
				-webkit-transition-delay: 0s;
				-ms-transition-delay: 0s;
				transition-delay: 0s;
				opacity: 0;
			}

				#viewer .inner .toggle {
					/* background-image: url("images/close-small.svg") !important; */
					background-size: 32px 32px;
				}

				body.fullscreen #viewer {
					-moz-transition-delay: 0.5s;
					-webkit-transition-delay: 0.5s;
					-ms-transition-delay: 0.5s;
					transition-delay: 0.5s;
					opacity: 1;
				}

		}
/* Main */

	#main {
		opacity: 1 !important;
		right: 0 !important;
	}

	/* body:before {
		content: 'Javascript is disabled :(';
		display: block;
		position: absolute;
		top: 50%;
		width: calc(100% - 22.5em * 0.333333333);
		height: 4em;
		margin-top: -2em;
		color: #282828;
		cursor: default;
		font-size: 3em;
		line-height: 4em;
		text-align: center;
		white-space: nowrap;
		left: 0;
	} */
</style>