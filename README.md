# Resize-by-ratio


function resizebyratio(divname, x, y, maxwidth) {
	$(divname).css("display", "none");
	var screenw = window.innerWidth-15;
	var screenh = window.innerHeight-20;
	var screenratio = screenw / screenh;
	var divratio = x / y;
	var divwidth = Math.min(screenw, maxwidth); 
	if (divratio <= 1) {
		var divwidth = screenh * x / y;
		if (divwidth == maxwidth) {		
			var divheight = maxwidth * y /x;
			var mtop = (screenh - divheight) / 2;
			jQuery(divname).css({"margin-top":mtop+"px"});
		}
		else {
			var divheight = screenh;
		};
		jQuery(divname).css({"height":divheight+"px", "width":divwidth+"px"});
	}
	else if (1 < divratio && divratio <= screenratio) {
		var divwidth = screenh * x / y;
		if (divwidth >= maxwidth) {
			var divheight = maxwidth * y /x;
			var mtop = (screenh - divheight) / 2;
			jQuery(divname).css({"margin-top":mtop+(screenh/100*3)+"px"});
			divwidth = maxwidth;
		}
		else {
			var divheight = screenh;
		};
		jQuery(divname).css({"height":divheight+"px", "width":divwidth+"px"});
	}		
	else { 
		var divheight = divwidth * y / x;
		var mtop = (screenh - divheight) / 2;
		jQuery(divname).css({"width":divwidth+"px", "height":divheight+"px", "margin-top":mtop+(screenh/100*3)+"px"});
	};
	jQuery(divname).css("display", "block");
};
