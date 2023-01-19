##### Prelim revision questions
[Questions from every topic that could be asked](https://www.dynamicmaths.co.uk/QuestionBank/get_questions_handler.php?levelQ=6&otherlevellist=empty&how=A&orderR=dateA&calc=CN&noQ=500&minmarks=0&maxmarks=999&NR=RN&interleaved=NA&MC=MCA&topics[]=221&topics[]=222&topics[]=223&topics[]=224&topics[]=253&topics[]=254&topics[]=255&topics[]=256&topics[]=257&topics[]=258&topics[]=259&topics[]=304&topics[]=260&topics[]=261&topics[]=262&topics[]=263&topics[]=298&topics[]=264&topics[]=265&topics[]=266&topics[]=267&topics[]=268&topics[]=269&topics[]=270&topics[]=271&topics[]=272&topics[]=281&topics[]=227&topics[]=228&topics[]=229&topics[]=230&topics[]=231&topics[]=232&topics[]=233&topics[]=234&topics[]=235&topics[]=236&topics[]=237&topics[]=238&topics[]=239&topics[]=240&topics[]=241&topics[]=242&topics[]=243&topics[]=244&topics[]=280&topics[]=205&topics[]=206&topics[]=207&topics[]=208&topics[]=209&topics[]=210&topics[]=211&topics[]=212&topics[]=213&topics[]=214&topics[]=215)
##### Sketching graphs of derived functions
* **The derivative is the gradient of the graph.** If the gradient is positive so must that point on the derivative (even if the point on the original graph has `y < 0`)
* (See below) The gradient decreases as the gradient decreases, then increases as the gradient increases
```desmos-graph
left=-40; right=40; top=400; bottom=-400;
---
f(x)=x^3+12x^2+50x-11
f(x)=3x^2+24x+50
```
<br/>

##### Trig Equations
**The simple ones**
$$\sqrt(2)*cos(x)+1=0$$
$$cos(x)=\frac{-1}{\sqrt(2)}$$
$$x =\frac{3\pi}{4}, x=\frac{5\pi}{4}$$

**The harder ones**
$$2sin(3x-60)\degree+1=0, 0 \le x < 180$$
$$sin(3x-60)=\frac{-1}{2}$$
$$3x-60=210\degree, 3x-60=330\degree$$
$$3x=270\degree, 3x=390\degree$$
$$x=90\degree, x=130\degree$$
$$x=10\degree, x=90\degree, x=130\degree$$

1. Rearrange to get the trig on it's own
2. Use exact values in non-calc or calculator to find $$\sin^{-1}(\frac{1}{2})=30\degree$$
3. Use the CAST diagram. Because of the negative we use the opposites (Cos and Tan instead of All and Sin) giving $$x=180+30, x=360-30$$ $$x=210\degree, x=390\degree$$
4. After rearranging for $x$ we get $$x=90\degree, x=130\degree$$ Now we need to take into account the period of one wave. Because we initlaly had $3x$, we divide 360 by 3, giving a period of 120. This means one full sine wave takes 120°
5. Finally we have to find all of the answers that fit within the given domain. $130-120=10$, $0 \le 10$ therefore 10 is another possible answer

**Another example**
$$3cos(2x)=1$$
$$cos(2x)=\frac{1}{3}$$
$$2x=1.231, 2x=2\pi-1.231$$
$$2x=1.231, 2x=5.052$$
$$x=0.616, x=2.53$$
$$x=0.616, x=2.53, x=3.76, x=5.67$$

1. Rearrange same as before to get the trig on it's own
2. Use a calculator to remove the trig $$cos^{-1}(\frac{1}{3})=1.231$$
3. Because the fraction was positive we are going to use the normal CAST values, All and Cos, giving $$2x=1.231, 2x=2\pi-1.231$$ We can then simplify to get $x$ on it's own, then look to the period to find our final solutions
4. We initially had $2x$, so our period is $2\pi/2=\pi$ which we need to account for so we add $\pi$ until we go out of the given domain $$x=0.616, x=2.53, x=0.616+\pi, x=2.53+\pi$$ $$x=0.616, x=2.53, x=3.76, x=5.67$$