### De Boor's Algorithm

De Boor的算法是对de Casteljau算法的普遍化。它提供了一种快速、稳定的数值方法，给定一个U可以在B-spline曲线上找到一个给定域中的u的点。

De Boor's algorithm is a generalization of de Casteljau's algorithm. It provides a fast and numerically stable way for finding a point on a B-spline curve given a u in the domain.


从多结的一个属性中回想一下，增加一个内结的倍率会减少这个结上的非零基础函数的数量。事实上，如果这个结的倍数为k，那么在这个结上最多有p - k + 1的非零基础函数。因此，在一个倍数为p的结上，只有一个非零基函数在这个结上的值是1，因为有了统一性的分割属性。让这个结为ui。如果u是ui，因为Ni，p(u)在[ui，ui+1)上是非零，所以曲线上的点p(u)正好受一个控制点pi的影响。更准确地说，我们实际上有p(u)=Ni，p(u)pi=pi!

Recall from a property of multiple knots that increasing the multiplicity of an internal knot decreases the number of non-zero basis functions at this knot. In fact, if the multiplicity of this knot is k, there are at most p - k + 1 non-zero basis functions at this knot. Consequently, at a knot of multiplicity p, there will be only one non-zero basis function whose value at this knot is one because of the property of partition of unity. Let this knot be ui. If u is ui, since Ni,p(u) is non-zero on [ui,ui+1), the point on the curve p(u) is affected by exactly one control point pi. More precisely, we actually have p(u) = Ni,p(u) pi = pi!

那么，这个有趣或者说有点奇怪的属性是什么呢？很简单：如果一个结u被插入p次后，在一条B-spline/NURBS曲线上，最后生成的新控制点就是曲线上与u相对应的点，为什么会这样呢？因为在插入u p次后，三角计算方案产生一个点。因为给定的B-spline/NURBS曲线必须通过这个新点，所以它是曲线上对应于u的点。

因此，这个观察结果为我们提供了在曲线上寻找p(u)的技术。我们只需将u插入p次，最后一点就是p(u)!

让我们先看一个例子，然后再继续往下看。下面是一条有7个控制点的4度NURBS曲线。为了计算出p(0.9)，u = 0.9被插入4(度)倍。第二和第三图是第一次和第二次插入后的结果。因此，在右下角附近增加了两个新的控制点。请注意，控制点的多轴线比原来的曲线更接近曲线。第三次插入后的结果在第四图中显示。我们又多了一个控制点；但曲线上的点还没有编号，因为它还不是控制点。第四次插入使这个结果发生了。因此，经过四次插入后，p(0.9)是一个控制点。

    
上一页讨论的一般结插入算法可以很容易地修改来实现我们的目的。首先要注意的是，我们只需要插入u足够的次数，使u成为一个倍数p的结。

输入：一个值u
输出：曲线上的点，p(u)

如果u位于[uk,uk+1)中，并且u !=uk，让h = p(即，插入u p次)和s = 0。
如果u = uk，并且uk是一个倍数s的结，让h = p - s（即，插入u p - s的时间）。
将受影响的控制点 pk-s、pk-s-1、pk-s-2、...、pk-p+1 和 pk-p 复制到一个新的数组中，并将它们重命名为 pk-s,0、pk-s-1,0、pk-s-2,0、...、pk-p+1,0。

对于 r := 1 到 h，做
对于i := k-p+r至k-s的i := k-p+r至k-s做
开始
让 ai,r = (u - ui) / ( ui+p-r+1 - ui )
让 pi,r = (1 - ai,r) pi-1,r-1 + ai,r pi,r-1
终点
pk-s，p-s为点p(u)。
在下图的左图中，所有的π，0's都在左列上。从第0列和系数ai,1，可以计算出 pi,1's。从这第一列和系数ai,2's，可以计算出第二列，以此类推。由于零点列上有(k-s)-(k-p)+1=p-s+1个点，而且每列上有一个点比前一列少一个点，所以需要用p-s列来减少该列上的点数为1，这就是最后一个点为pk-s,p-s的原因。右图是切角的过程。

 
虽然这个过程看起来和de Casteljau的算法中得到的过程很像，但实际上它们之间有很大的区别。首先，在de Casteljau的算法中，除法点是用一对数字1-u和u来计算的，这两个数字在整个计算过程中永远不会改变，而在de Boor的算法中，这对数字是不同的，取决于列号和控制点的数量。第二，de Casteljau算法可以用于曲线细分，而de Boor算法中产生的中间控制点并不能满足这个目的。第三，在de Boor的算法中，只有p+1影响的控制点参与计算，而de Casteljau的算法使用所有的控制点。由于控制点pk-pk到pk定义了一个包含结跨度[uk，uk+1]上的曲线段的凸壳，所以de Boor算法的计算是在相应的凸壳中进行的。


举个例子
假设我们有一条3度B线曲线（即p=3），由7个控制点p0，...，p6（即n=6）和11个结向量（即m=10）定义的3度B线曲线。
u0 = u1 = u2 = u3 u4 u4 u5 u6 u7 = u8 = u9 = u10
0 0.25 0.5 0.75 1
根据这些信息，我们将计算出p(0.4)。对于de Boor的算法，这相当于将u = 0.4插入三次。由于u=0.4不是一个现有的结，s=0，u=0.4在[u4，u5)中，因此受影响的控制点为p4，p3，p2和p1。下面是计算方案。

 
让我们计算第二列。所涉及的a系数为

a4,1 = (u - u4) / ( u4+3 - u4) = 0.2
a3,1 = (u - u3) / ( u3+3 - u3) = 8/15 = 0.53
a2,1 = (u - u2) / ( u2+3 - u2) = 0.8
因此，第一列的计算方法如下。
p4,1=(1-a4,1)p3,0+a4,1p4,0=0.8p3,0+0.2p4,0
p3,1 = (1 - a3,1)p2,0 + a3,1p3,0 = 0.47p2,0 + 0.53p3,0
p2,1=(1 - a2,1)p1,0 + a2,1p2,0=0.2p1,0 + 0.8p2,0
为了计算第二列，我们需要以下系数。






So, what is the point of this interesting or somewhat strange property? Simple: if a knot u is inserted p times to a B-spline/NURBS curve, the last generated new control point is the point on the curve that corresponds to u. Why is this so? After inserting u p times, the triangular computation scheme yields one point. Because the given B-spline/NURBS curve must passe this new point, it is the point on the curve corresponding to u. Note that this argument holds even if u is inserted as an existing knot.

Therefore, this observation provides us with a technique for finding p(u) on the curve. We just simply insert u p times and the last point is p(u)!

Let us take a look at an example before move on. The following is a degree 4 NURBS curve with 7 control point. To compute p(0.9), u = 0.9 is inserted 4 (the degree) times. The second and third figures show the results after the first and second insertion. Thus, two new control points are added near the lower right corner. Please note that the control polyline is closer to the curve than the original. The result of the third insertion is shown in the fourth. We have one more control point; but the point on curve is not yet numbered since it is not yet a control point. The fourth insertion makes this happen. Therefore, after four insertion, p(0.9) is a control point.

    
The general knot insertion algorithm discussed on the previous page can be easily modified to fulfill our purpose. First note that we only need to insert u enough number of times so that u becomes a knot of multiplicity p. If u is already a knot of multiplicity s, then inserting it p - s times would be sufficient.

Input: a value u
Output: the point on the curve, p(u)

If u lies in [uk,uk+1) and u != uk, let h = p (i.e., inserting u p times) and s = 0;
If u = uk and uk is a knot of multiplicity s, let h = p - s (i.e., inserting u p - s time);
Copy the affected control points pk-s, pk-s-1, pk-s-2, ..., pk-p+1 and pk-p to a new array and rename them as pk-s,0, pk-s-1,0, pk-s-2,0, ..., pk-p+1,0;

for r := 1 to h do
for i := k-p+r to k-s do
begin
Let ai,r = (u - ui) / ( ui+p-r+1 - ui )
Let pi,r = (1 - ai,r) pi-1,r-1 + ai,r pi,r-1
end
pk-s,p-s is the point p(u).
In the following left diagram, all pi,0's are on the left column. From the zero-th column and coefficients ai,1, one can compute pi,1's. From this first column and coefficients ai,2's, the second column is computed and so on. Since there are (k-s)-(k-p)+1 = p-s+1 points on the zero-th column and since each column has one point less than the previous one, it takes p-s columns to reduce the number of points on that column to 1. This is why the last point is pk-s,p-s. The right diagram shows the corner-cutting process.

 
While this process looks like the one obtained from de Casteljau's algorithm, in fact they are very different. First, under de Casteljau's algorithm, the dividing points are computed with a pair of numbers 1 - u and u that never change throughout the computation procedure, while under de Boor's algorithm these pairs of numbers are different and depend on the column number and control point number. Second, de Casteljau's algorithm can be used for curve subdivision, while the intermediate control points generated by de Boor's algorithm are not sufficient for this purpose. Third, in de Boor's algorithm only p+1 affected control points are involved in the computation, while de Casteljau's algorithm uses all control points. Since control points pk-p to pk define a convex hull that contains the curve segment on knot span [uk, uk+1), the computation of de Boor's algorithm is performed within the corresponding convex hull.


An Example
Suppose we have a degree 3 B-spline curve (i.e., p = 3) defined by seven control points p0, ..., p6 (i.e., n = 6) and the following knot vector of 11 knots (i.e., m = 10):
u0 = u1 = u2 = u3	u4	u5	u6	u7 = u8 = u9 = u10
0	0.25	0.5	0.75	1
Based on these information, we shall compute p(0.4). For de Boor's algorithm, this is equivalent to inserting u = 0.4 three times. Since u = 0.4 is not an existing knot, s = 0 and u = 0.4 is in [u4, u5), the affected control points are p4, p3, p2 and p1. The following is the computation scheme:

 
Let us compute the second column. The involved a coefficients are

a4,1 = (u - u4) / ( u4+3 - u4) = 0.2
a3,1 = (u - u3) / ( u3+3 - u3) = 8/15 = 0.53
a2,1 = (u - u2) / ( u2+3 - u2) = 0.8
Therefore, the first column is computed as follows:
p4,1 = (1 - a4,1)p3,0 + a4,1p4,0 = 0.8p3,0 + 0.2p4,0
p3,1 = (1 - a3,1)p2,0 + a3,1p3,0 = 0.47p2,0 + 0.53p3,0
p2,1 = (1 - a2,1)p1,0 + a2,1p2,0 = 0.2p1,0 + 0.8p2,0
To compute the second column, we need the following coefficients:

a4,2 = (u - u4) / (u4+3-1 - u4) = 0.3
a3,2 = (u - u3) / (u3+3-1 - u3) = 0.8
The points are
p4,2 = (1 - a4,2) p3,1 + a4,2p4,1 = 0.7p3,1 + 0.3p4,1
p3,2 = (1 - a3,2) p2,1 + a3,2p3,1 = 0.2p2,1 + 0.8p3,1
Finally, since a4,3 = (u - u4)/ (u4+3-2 - u4) = 0.6, the final point is
p4,3 = (1 - a4,3)p3,2 + a4,3p4,2 = 0.4p3,2 + 0.6p4,2
This is the point on the curve corresponding to u = 0.4.
Please notice the similarity of those intermediate polylines generated by de Boor's algorithm and those generated by de Casteljau's algorithm.

Please also note that u is not a knot in this example. If u is a knot, the computation would be easier since we will have fewer number of affected control points.


De Boor's Algorithm for NURBS Curves
De Boor's algorithm also works for NURBS curves. We just multiply every control point by its weight converting the NURBS curve to a 4D B-spline curve, perform de Boor's algorithm on this 4D B-spline curve, and then project the resulting curve back by dividing the first three components with the fourth and keeping the fourth component as its new weight.


a4,2 = (u - u4) / (u4+3-1 - u4) = 0.3
a3,2 = (u - u3) / (u3+3-1 - u3) = 0.8
各个点是
p4,2 = (1 - a4,2) p3,1 + a4,2p4,1 = 0.7p3,1 + 0.3p4,1
p3,2 = (1 - a3,2) p2,1 + a3,2p3,1 = 0.2p2,1 + 0.8p3,1
最后，由于a4,3=(u-u4)/(u4+3-2-2-u4)=0.6，所以最后一点是
p4,3 = (1 - a4,3)p3,2 + a4,3p4,2 = 0.4p3,2 + 0.6p4,2
这是曲线上对应于u=0.4的点。
请注意de Boor算法产生的中间多线和de Casteljau算法产生的中间多线的相似性。

还请注意，在这个例子中，u不是一个结。如果u是一个结，计算会更容易，因为我们将有更少的控制点。


De Boor的NURBS曲线算法
De Boor的算法同样适用于NURBS曲线。我们只需将NURBS曲线的每个控制点乘以其权重，将NURBS曲线转化为4D B-spline曲线，在这条4D B-spline曲线上执行de Boor算法，然后将前三个分量与第四个分量相除，保留第四个分量作为新的权重，就可以将得到的曲线投影回来。
