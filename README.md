<!DOCTYPE html>
<html>
<head>
  <meta http-equiv="Content-Type" content="text/html; charset=utf-8"/>
  <title>HTML5 Canvas and Audio Experiment</title>
  
  <meta name="keywords" content="html5, canvas, experiment" />
  <meta name="description" content="An html5 canvas experiment by 9elements.com" />
  
  <link rel="image_src" href="http://9elements.com/io/projects/html5/canvas/experiment_preview.png" />
  
  <script src="processing.min.js" type="text/javascript" charset="utf-8"></script>
  <script src="jquery-1.6.1.min.js" type="text/javascript" charset="utf-8"></script>
  <script src="apt18.js" type="text/javascript" charset="utf-8"></script>
  
  <style type="text/css" media="screen">
    body {
        background: #000;
        color: #aaa;
        font-family: Helvetica, sans-serif;
  	margin:0;
		padding:0;
		overflow:hidden;
    }

	a {
		text-decoration:none;
	}
	
    #theapt {
    }
    #stuff {
		postion:absolute;
    }
	#tweet {
		font-family:Helvetica, Arial;
		position:absolute;
				
		top:400px;
		left:260px;
		
		width:640px;
	}
	
	#tweet h1 {
		display:block;
		font-family:Helvetica, Arial;
		font-size:40px;
		font-weight:bold;
		color:#fff;
		margin:0 0 10px 0;
		padding:0;
	}
	
	#tweet strong {
		display:block;
		font-size:16px;
	}
	
	#about {
		font-size:11px;
		position:absolute;
		font-weight:normal;		
		bottom:20px;
		left:20px;
	}
	
	#social {
		font-size:11px;
		position:absolute;
		font-weight:normal;		
		bottom:13px;
		right:20px;
		width: 120px;
	}

	#about a {
		color: #59cdec;
	}
	
	#watchlater {
	  font-size:11px;
		position:absolute;
		font-weight:normal;		
		bottom:0px;
		left: 50%;
		margin-left: -95px;
		width: 378px;
		height: 85px;
	  line-height: 1.5;
	  
	  -webkit-animation: 'wobble' 5s;
  	-webkit-animation-iteration-count: infinite;
	}
	
	@-webkit-keyframes 'wobble' {
	  0% { -webkit-transform: translate(0, 0) rotate(0deg) scale(1); }
	  75% { -webkit-transform: translate(0, 0) rotate(0deg) scale(1); }
  	80% { -webkit-transform: translate(0, 0) rotate(2deg) scale(1); }
  	85% { -webkit-transform: translate(0, 0) rotate(-2deg) scale(1.1); }
  	90% { -webkit-transform: translate(0, 0) rotate(2deg) scale(1); }
  	95% { -webkit-transform: translate(0, 0) rotate(-2deg) scale(0.9); }	
  	100% { -webkit-transform: translate(0, 0) rotate(0deg) scale(1); }
  }
  
	
	#watchlater h6 {
	  font-size: 11px;
	  margin: 0;
	  padding: 20px 0 0 0;
	  text-transform: uppercase;
  }
  
  #watchlater .watchlater-claim{
    color: #fff;
  }

  #watchlater .watchlater-comment{
    color: #aaa;
  }
	
	#watchlater a#watchlater-image {
	  float:left;
	  margin-right: 10px;
	}

	#watchlater a#watchlater-image img {
	  border: 0;
  }
	
	#watchlater a {
	  color: #59cdec;
	}
	
  </style>
</head>
<body>
<script src="modernizr-0.9.min.js"></script>
<canvas id="theapt" width="100" height="100"></canvas>
<div id="tweet">
	LOADING
</div>
<div id="stuff">
	<audio id="audio">  
		Your browser does not support the <code>audio</code> element.  
	</audio>
</div>
<div id="about">
    Made with love by <a href="http://9elements.com/"><strong>9elements.com</strong></a>
</div>
<div id="social">
  <!-- Place this tag in the <head> of your document-->
  <link href="https://plus.google.com/115296814382489811952" rel="publisher" />

  <!-- Place this tag where you want the badge to render-->
  <a href="https://plus.google.com/115296814382489811952?prsrc=3" style="text-decoration:none;"><img src="https://ssl.gstatic.com/images/icons/gplus-16.png" alt="" style="border:0;width:16px;height:16px;"/></a>
  on Google+
  <br />
  <iframe src="http://www.facebook.com/plugins/like.php?locale=en_US&href=www.facebook.com%2F9elements&amp;send=false&amp;layout=button_count&amp;width=77&amp;show_faces=false&amp;action=like&amp;colorscheme=light&amp;font=lucida+grande&amp;height=20" scrolling="no" frameborder="0" style="border:none; overflow:hidden; width:77px; height:20px;" allowTransparency="true"></iframe>
  <a href="https://twitter.com/9elements" class="twitter-follow-button" data-show-count="false">Follow @9elements</a>
  <script src="http://platform.twitter.com/widgets.js" type="text/javascript"></script>
</div>
<div id="watchlater">
  <a id="watchlater-image" href="http://itunes.apple.com/us/app/watchlater/id423572879?mt=8&affId=1728362&ign-mpt=uo%3D4"><img src="watchlater-2.0.png" alt="watchlater" title="watchlater"></a>
  <div class="watchlater-content">
    <h6>We also made</h6>
    <div class="watchlater-claim"><a href="http://itunes.apple.com/us/app/watchlater/id423572879?mt=8&affId=1728362&ign-mpt=uo%3D4"><strong>watchlater for iPhone and iPad</strong></a></div>
    <div class="watchlater-comment">"The Instapaper for Videos" - <span>gigaOM</span></div>
  </div>
</div>
<script type="text/javascript">
	var gaJsHost = (("https:" == document.location.protocol) ? "https://ssl." : "http://www.");
	document.write(unescape("%3Cscript src='" + gaJsHost + "google-analytics.com/ga.js' type='text/javascript'%3E%3C/script%3E"));
	</script>
	<script type="text/javascript">
	try {
	var pageTracker = _gat._getTracker("UA-7994748-1");
	pageTracker._trackPageview();
	} catch(err) {}
</script>
</body>
</html>
