
#### 1. Alternative methods to display the same data
_as in Figure 1 (circos plot data + tabular data)_

---

> From Figure 1, I understand that the current GUI is composed of:
- TabularData  (standard GUI)
- Datavizualisation part:
 - Overview (circos plot)
 - Zoomed section
 - Horizontal diagram of genes
 

#### 2. Ideas for how the user could navigate the circos plot intuitively 
_to look at both details and an overview as appropriate_

---

> One of the most important parts of the project, as it determines the overall usability of the GUI and is the entry point for the user.
It is very difficult to answer this question not knowing the business data. 
This part of visualization design should be done with a good knowledge of data being manipulated and especially after understanding what users want to do:
- Easy navigation?
- Pattern recognitions
- Discover correlations
- ... ?

> However, I used your data from your example to make my own graph (with Nodebox3). Here the following result. 
Nothing special, not knowing what is important to users and having no definition of data.

![](https://raw.github.com/ig2gi/perso/master/sophia_genetics/circos_min.png?login=ig2gi&token=e4f8c2757d071f069abbebfc32ceaa5e)
[>>>>> view large image](https://raw.github.com/ig2gi/perso/master/sophia_genetics/circos.png?login=ig2gi&token=4d2a8df49b153815caa1dc772cc93309)

> I drew the chromosom HS13 (perhaps it's not a chromosome?) in a linear and vertical way, whose function is to be a selector of a portion of chromosom. The corresponding portion in the circos graph is then selected. The user can then zoom in on that area (sector).
Instead of selecting a rectangle, the user slides the selection box vertically. (a single movement instead of two, more intuitive).  
Again, with a thorough knowledge of the data it would be easier to give proper notice.



#### 3. An estimate for the time you would require to produce the circos functionality, 
_and how you would go about it (what technologies would you choose)_

---

> I think the choice of JavaFX seems a good choice, especially with regard to characteristics such as application packaging and ease of integration with the customer.  
It seems that we can also make a very good standard user interface  (wide variety of built-in controls, tabular data, ...).  
However, for the data visualization part, although we can implement it directly into JavaFX (with the graphics primitives available) I will not recommand this choice for the following reasons:
- After reading some forums on the comparison between technologies / frameworks devoted to data visualization (such as processing, or d3.js js) and JavaFX, the advantage is clearly on the side of specialized technologies.
- By experience, although expert in JAVA, I advocate the use of dynamic language and not strongly typed (python, javascript, ..) to realize data visualization. In addition, these languages ​​are quite testable like JAVA.
- As you can embed Web content in JavaFX (webcomponent with webkit engine), the use of standards SVG + Javascript + as CSS can seem quite preferred with the following benefits:
 - Standards
 - Using the powerful graphical features of each standard (masking, animations, clipping, gradient, conditional styling, events, ...)
 - Can develop (and deploy) the visualization engine independently of the GUI in JavaFX.
 - You can use D3.js or other graphics framework
 - web component (DOM)  and other JavaFX components can communicate each other.


![](https://raw.github.com/ig2gi/perso/master/sophia_genetics/architecture.png?login=ig2gi&token=58043192f58c8153020f8a242057c7c6)

> We have to validate of course the performance of the javaFx web component (and PRISM graphic engine)  
Regarding the time required to reproduce the functionality of circos.

> I distinguish several aspects:
- Basic graph
- Animations
- Interactivity with the user
- Dynamic data

> I will vote only on the implementation of graph circos (static) SVG + JavaScript + CSS + d3.js:  
30j / h (javascript integration environment + unit tests +  frameworks)


#### 4. What do you expect to be the bottleneck in producing the circos graphic dynamically 
_(ie in near real time) – are you confident it can be done ?_

---

> The number of data is not that important (30kb compressed), the network will not  be a bottleneck.
So I see two main sources of bottleneck:
- Graphical rendering
- Data mining

> For the second, I do not know if there is data mining on the client (or only on the server, or not at all?).
If the data is ready to be viewed directly without prior transformations (sorting, grouping, statistics, combinations, ...)  then the second point is not relevant.  
Remains the first point, the graphics rendering.  
JavaFX seems to have a new graphics engine (PRISM) on which we can count but remains to be tested!
Although the data are not so many, it may still represent a large number of graphics units, for example:  
HS13: 1600 (snp) + 800 (coverage)
with HS17 (x2), we arrive at a minimum of at least 5000 graphic elements. (counting a brutal way!).  

> A good knowledge of technologies/frameworks used and a good modeling are the keys to have a good performance (and of course the engine PRISM itself!)
