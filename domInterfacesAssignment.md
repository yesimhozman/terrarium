I found this function after I open the page source of https://www.w3schools.com/js/js_htmldom.asp page. 
In this webpage, there is a top bar and below that top bar, there is the sticky navigation bar. The sidebar is also sticky. So, when people scroll down the page, the top of the sidebar should change to be responsive. In this function, there are two variables. w is for inner width and top is declaring scrolltop function. To understand the function clearly, I attached scrolltop function below. With this function, we will get the pageYOffset value as a number. When the user scrolls the page, the distance to the top will change according to the conditions which are presented in if // else statements. 

With this function, we can change the style of the document. Thanks to Document Object Model representation, we can manipulate the objects. They used "document" objects to manipulate the document itself. They used getElementById() method to access the elements. 

We can say that this function is for dynamic styling. 

function fix_sidemenu() {
  var w, top;
  w = window.innerWidth || document.documentElement.clientWidth || document.body.clientWidth;
  top = scrolltop()    
 if (top == 0) {
      document.getElementById("sidenav").style.top = "118px";      
    }
    if (top > 0 && top < 73) {
      document.getElementById("sidenav").style.top = (118 - top) + "px";      
    }
    if (top > 73) {
      document.getElementById("sidenav").style.top = "44px";
      if (w > 992) {document.getElementById("leftmenuinner").style.paddingTop = "44px";}
      document.getElementById("belowtopnav").style.paddingTop = "44px";    
      document.getElementById("topnav").style.position = "fixed";
      document.getElementById("topnav").style.top = "0";
      document.getElementById("myAccordion").style.paddingTop = "44px";
      document.getElementById("googleSearch").style.position = "fixed";
      document.getElementById("googleSearch").style.top = "0";
      document.getElementById("google_translate_element").style.position = "fixed";
      document.getElementById("google_translate_element").style.top = "0";
    } else {
      if (w > 992) {
        document.getElementById("leftmenuinner").style.paddingTop = (118 - top) + "px";
      } else { //ELSEN ER NY
        document.getElementById("leftmenuinner").style.paddingTop = 0;
      }
      document.getElementById("belowtopnav").style.paddingTop = "0";
      document.getElementById("myAccordion").style.paddingTop = "0";
      document.getElementById("topnav").style.position = "relative";
      document.getElementById("googleSearch").style.position = "absolute";
      document.getElementById("googleSearch").style.top = "";
      document.getElementById("google_translate_element").style.position = "absolute";
      document.getElementById("google_translate_element").style.top = "";
    }
    }

    function scrolltop() {
  var top = 0;
  if (typeof(window.pageYOffset) == "number") {
    top = window.pageYOffset;
  } else if (document.body && document.body.scrollTop) {
    top = document.body.scrollTop;
  } else if (document.documentElement && document.documentElement.scrollTop) {
    top = document.documentElement.scrollTop;
  }
  return top;
}