jQuery code for web elements dimension optimizing

Hi. I'm Silvia Malavasi, web designer.

I always fight with giving html elements the right size and center when designing a full screen website. This little script allow you to have your div centered and full sized and still keep its original aspect razio. No cuts and no stretches, just the maximum width or height your screen allows. So you can have a perfect background image and a right-sized div to contain it. Your site can now fit in this div (if you don't want your site to scroll down). You can always use resize_by_ratio without a real background image, just to give your content div a fullscreen dimension.

You can find an example of resize_by_ratio here: http://www.hostservizi.it/

Let's see how to do it.

EXAMPLE: 	you want your MYCONTENT div fits on screen. MYCONTENT contains an image (MYIMAGE) wich dimensions are 1600px x 1000px. 

					HTML
					
					<div id="MYCONTENT">
						<img src="MYIMAGE">
					</div>
					
					CSS
					
					#MYCONTENT  {
						margin: auto;
						left: 0;
						right:0;
						display: none;
						}
					
					#MYCONTENT  img {
						width: 100%;
						height: 100%;
					}


The function resizebyratio gets 4 parameters:
  divname: the name of the div to resize, in this case #MYCONTENT
  x: the image width, in this case 1600
  y: the image height, in this case 1000
  maxwidth: the maximum width of the content (in this case 1600, cause we don't want to loose the image quality on bigger screens or make the site too big).
  
Copy the HTML, the CSS and the JS code in your site and launch resizebyratio.
  
$(document).ready(resizebyratio(#MYCONTENT, 1600, 800, 1600));
