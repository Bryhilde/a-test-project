## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/Bryhilde/a-test-project/edit/master/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/Bryhilde/a-test-project/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
<html>

<head><title>pmv-sample-03</title>

<script type="text/javascript">
<!--
    function golden(form){
      var rh,tr,
          tcl,b,c,d,e,
          icl,v,
          xl,xu,i,x,r,d,
          x1,x2,
          f1,f2,f,fx,
          pmv1,pmv2,
          ta,pmv,ppd,         
     rh = eval(form.rh.value);
      m = eval(form.m.value);
      w = eval(form.w.value);
     tr = eval(form.tr.value);
    icl = eval(form.icl.value);    
      v = eval(form.v.value);
                       
        r = (Math.pow(5,0.5)-1)/2
       xl = 16
       xu = 30
        i = 0
        d = r*(xu-xl)
       x1 = xl + d
       x2 = xu - d
     pmv1 = pmv(rh,w,m,tr,icl,v,x1)
       f1 = ppd(pmv1)
     pmv2 = pmv(rh,w,m,tr,icl,v,x2)
       f2 = ppd(pmv2)
       if (f1 > f2) {
           x = x1
           f = f1
          }
           else{
           x = x2
           f = f2
          }
           while(i < 30 ){
           d = r*d                  
           if (f1 < f2) {
           xl = x2
           x2 = x1
           x1 = xl + d
           f2 = f1
           pmv1 = pmv(rh,w,m,tr,icl,v,x1)
           f1 = ppd(pmv1)
          }else{
           xu = x1
           x1 = x2
           x2 = xu - d
           f1 = f2
           pmv2 = pmv(rh,w,m,tr,icl,v,x2)
           f2 = ppd(pmv2)
          }
           i = i + 1
           if (f1 < f2){
           x = x1
          fx = f1 
          }else{
            x = x2
           fx = f2
          }
          }
                   
            ta = Math.round(x)
           pmv = pmv(rh,w,m,tr,icl,v,ta)
           ppd = ppd(pmv)  
           form.ta.value = ta
           form.pmv.value = pmv
           form.ppd.value = ppd
//--------------------------------------------------------------
    function pmv(rh,w,m,tr,icl,v,ta){
             
      var rh,ta,tr,Pa,
          pmv,pmv1,pmv2,
          tcl,b,c,d,e,
          icl,rcl,
          hc,v,
          con,s,factor,
      factor = 500;
           s = 0;
      pa = (rh/100)*0.1333*Math.exp(18.6686-4030.183/(ta+235)); 
            
     rcl = 0.155*icl;
     fcl = 1.05+0.65*rcl;
      hc = 12.1*Math.pow(v,0.5);
     do {
            b = 3.05*(0.255*(35.7-0.0285*m)-3.36-pa);
            c = 0.42*((m-w)-58);
            d = 1.73E-2*m*(5.867-pa);
            e = 1.4E-3*m*(34-ta);  
          tcl = 35.7-0.0275*m-rcl*(m-w-b-c-d-e-s);
         pmv1 = 5.67E-8*0.95*0.77*fcl*(Math.pow((tcl+273),4)-Math.pow((tr+273),4));
         pmv2 = fcl*hc*(tcl-ta);
          con = m-w-b-c-d-e-pmv1-pmv2-s;
         if (con > 0){
	     s= s+factor;
	     factor=factor/2;
	 }
	  else {
	     s=s-factor;
	 }     
     }while (Math.abs(con) > 0.01);
     pmv = (0.303*Math.exp(-0.036*m)+0.028)*((m-w)-pmv1-pmv2-b-c-d-e);
     return pmv
}
//------------------------------------------------------------------
  
    function ppd(pmv){
     var pmv,ppd,
               
     ppd = 100-95*Math.exp(-0.03353*Math.pow(pmv,4)-0.2179*Math.pow(pmv,2)); 
     return ppd
}
}
--></script>

<form>

<table width = 500 border = 1>

<tr><td>

PMV-SAMPLE<p>

  m = <input type = text value = 70 name = m  > (w/m2)<p>
  w = <input type = text value = 0 name = w  > (w/m2)<p>
 tr = <input type = text value = 22 name = tr > (c)   <p>
 rh = <input type = text value = 50 name = rh > (%)   <p>
icl = <input type = text value = 1 name = icl> (clo) <p>
  v = <input type = text value = 0.1 name = v  > (m/s) <p> 

<input onClick = golden(form) type = button value = submit ><p>

 ta = <input value = ta name = ta><p>
pmv = <input value = pmv name = pmv><p>
ppd = <input value = ppd name = ppd><p>


</td></tr></table>

</form>
</body>

</html>
