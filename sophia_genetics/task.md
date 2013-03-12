## Introduction



## Tasks
#### 1. Alternative methods to display the same data
_as in Figure 1 (circos plot data + tabular data)_

> From Figure 1, I understand that the current GUI is composed of:
- TabularData  (standard GUI)
- Datavizualisation part:
 - Overview (circos plot)
 - Zoomed section
 - Horizontal diagram of genes
 

#### 2. Ideas for how the user could navigate the circos plot intuitively 
_to look at both details and an overview as appropriate_

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



![](https://raw.github.com/ig2gi/perso/master/sophia_genetics/architecture.png?login=ig2gi&token=58043192f58c8153020f8a242057c7c6)


#### 4. What do you expect to be the bottleneck in producing the circos graphic dynamically 
_(ie in near real time) – are you confident it can be done ?_


## Conclusion

