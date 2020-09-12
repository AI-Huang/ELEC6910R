4.30

# TA

# Keywords

Meanshift

Flashback on Data Deceleration

Schedule Table File Link
The schedule file in Canvas is out of date, please follow this link for schedule reference:
https://drive.google.com/open?id=1Pksy_Vv-E7dBS923mhQUfk9pMQadKK8K

# LecQues11.pdf

Recap1  
A true(only when x and y are as y = kx + b)  
B no  
C no  
D yes(seems like A is false)

Recap2  
A yes, but don't really invest with that, just a warning(many professor lost so much with their papar work, ha ha), and this is just linear regression? come on  
B yes  
C yes, basicly, discrete space is the sub set of continues space, for continues space its ok, then definitely ok for the sub set (maybe we should take some math like Lie algebra, as well, I know the TA pretty well)  
D no, its prediction, no control. for control with prediction, that doesn't count

Q1:  
B A  
Regularisation is “Maximize a posteriori"  
Regression “Maximum Likelihood"

Q2  
p x prior  
p o evidence  
p x|o posterior  
p o|x likelihood  
refer to https://en.wikipedia.org/wiki/Bayes%27_theorem

# LecQues11-sampling.pdf

Q1  
BC  
Q2  
A false  
B true state-weighting is the formal step of resampling, which will be definite after that  
and I guess maybe an init state-weighting is important, like K-means  
just my understanding, welcome for discussion

C false D true  
E nope, gaussion process  
diff understanding refer to wiki  
https://en.wikipedia.org/wiki/Particle_filter

Q3  
A Yes, just google Gazebo SLAM  
B Yes  
C nope (environment adapting, sensor adapting, etc, just a simple example, how about camera resolution, simulating and real one are definitely the same? For real robot like Auto Vehicle, the demands are pretty high)  
D no, its SLAM, refer to https://answers.ros.org/question/239143/how-does-gmapping-work/

# LecQues14-gp-kernel.pdf

Recap 1  
covariance  
Recap 2  
A true  
B false  
C false  
refer to this:

> This paper introduces Gaussian Process Dynamical Models (GPDM) for ... In contrast, existing nonlinear models can model complex dynamics, but ... resulting Gaussian Process Dynamical Model (GPDM) is fully defined by a set of low- dimensional representations of the training data, with both dynamics and observation .

D true

Q1  
A yes  
B well i guess nope, just take some extreme example like deciding 255 255 255 and 000 000 000, a simple if is ok, but for ML?  
C yep ^\_^ pretty cool  
D yes, refer to https://www.aaai.org/ocs/index.php/AAAI/AAAI17/paper/download/14239/13764  
E yes, a commom knowledge, refer to loss function

Q2  
A yes  
B nope, likely/close for regression, seperated for classification, the formal minimum the error, while the latter maximum the distance between classes, just my understanding  
C nope, no absolutely, depends on class distribution (like crosses between classes, that's why we need SVM)  
D yes

# LecQues15-icp.pdf|Lec10_ICP_k.pdf

icp
Q2, true about ICP  
iterative? yes  
no  
yes  
no, can still work  
yes

Q3  
no, not only or 2D data  
yes  
not easily GPU FPGA k-d tree a lot of references

Q4  
yes, density  
yes, algorithms  
no, selecting neighbours, no effect  
yes, pre-proc is very important

Q5  
(homogeneous)
distance  
eigenspace of distance matrix  
error mean

# LecQues16_face_meanshift.pdf|

Recap 1:  
no  
yes  
yes

Q1  
true  
no, since uniform  
yes,  
no? i remember ming said, but i do not understand why the dataset size has no effect

Q2  
true  
true yep many regarding papers,  
true same as above, many papers(i wonder how many paper there are in the world, and every field)  
true, use likely info  
false, no posteriori probability

MLE max likely hood
MAP Maximum a posteriori estimation

Q3  
No, its async/step by step  
Of course, I've tried it when UG, it does have local optima(maybe i can bring out the wheel I made for this course)  
Yes,  
nope

========== flag

feature, data

true

recap4 no

q1
yes
no
yes
no

q2

Meanshift

kMeans

q2
no
no
no
max like
MAP

kMeans

Matlab Code

下课问一下老板。。。

K-Mean for image color segmentation

deep learning

reinforcement learning

dl front end

rl how to describe state policy,

review the slides first

Exercise K-means
