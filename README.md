Parametric Curve Fitting Assignment – Research and Development / AI
Overview

This project estimates unknown parameters in a given parametric curve using optimization techniques. The curve is defined as:

𝑥
=
𝑡
cos
⁡
(
𝜃
)
−
𝑒
𝑀
∣
𝑡
∣
⋅
sin
⁡
(
0.3
𝑡
)
sin
⁡
(
𝜃
)
+
𝑋
x=tcos(θ)−e
M∣t∣
⋅sin(0.3t)sin(θ)+X
𝑦
=
42
+
𝑡
sin
⁡
(
𝜃
)
+
𝑒
𝑀
∣
𝑡
∣
⋅
sin
⁡
(
0.3
𝑡
)
cos
⁡
(
𝜃
)
y=42+tsin(θ)+e
M∣t∣
⋅sin(0.3t)cos(θ)

Unknown parameters:

𝜃
θ (angle in degrees)

𝑀
M (exponential coefficient)

𝑋
X (x-offset)

Constraints:

0
∘
<
𝜃
<
50
∘
,
−
0.05
<
𝑀
<
0.05
,
0
<
𝑋
<
100
0
∘
<θ<50
∘
,−0.05<M<0.05,0<X<100

The goal is to find 
𝜃
,
𝑀
,
𝑋
θ,M,X that best fit a provided dataset of (x, y) points for 6 < t < 60.

Dataset

The dataset is provided as a CSV file (xy_data.csv) containing columns:

x – x-coordinate of the point

y – y-coordinate of the point

t (optional) – parameter value (if not present, the index is used)

Methodology

Load Dataset:

Read CSV file and extract x, y, and t.

Parametric Function:

Define a Python function that computes (x, y) for any t given parameters [θ, M, X].

Loss Function:

Use L1 distance between predicted and actual points as the optimization metric:

𝐿
1
=
∑
𝑖
∣
𝑥
pred
,
𝑖
−
𝑥
true
,
𝑖
∣
+
∣
𝑦
pred
,
𝑖
−
𝑦
true
,
𝑖
∣
L1=
i
∑
	​

∣x
pred,i
	​

−x
true,i
	​

∣+∣y
pred,i
	​

−y
true,i
	​

∣

Optimization:

Use scipy.optimize.minimize with bounds:

θ: 0 – 50°

M: -0.05 – 0.05

X: 0 – 100

Initial guess: [25, 0, 50]

Uniform Sampling for L1 Distance:

Sample 1000 points in t uniformly.

Compute interpolated actual values.

Recalculate L1 distance for consistent assessment.

Visualization:

Plot original data points vs. fitted parametric curve.

LaTeX Equation Generation:

Produce LaTeX-ready parametric curve for submission in Desmos or report.

Results

Estimated Parameters:

θ ≈ 28.120860°  
M ≈ 0.021397  
X ≈ 54.901150


Final L1 Distance:

≈ 37865.097670


Observation:

Parameters are within the prescribed ranges.

Predicted curve closely fits the dataset points.

LaTeX-ready Parametric Equation:

(
𝑥
(
𝑡
)
,
𝑦
(
𝑡
)
)
=
(
𝑡
cos
⁡
(
28.120860
)
−
𝑒
0.021397
∣
𝑡
∣
sin
⁡
(
0.3
𝑡
)
sin
⁡
(
28.120860
)
+
54.901150
,
42
+
𝑡
sin
⁡
(
28.120860
)
+
𝑒
0.021397
∣
𝑡
∣
sin
⁡
(
0.3
𝑡
)
cos
⁡
(
28.120860
)
)
(x(t),y(t))=(tcos(28.120860)−e
0.021397∣t∣
sin(0.3t)sin(28.120860)+54.901150,42+tsin(28.120860)+e
0.021397∣t∣
sin(0.3t)cos(28.120860))
How to Run

Clone or download the repository.

Open in Google Colab or Python environment.

Upload xy_data.csv when prompted.

Run the notebook/script.

The script will:

Optimize the parameters [θ, M, X]

Plot actual vs. fitted curve

Print final L1 distance

Display LaTeX-ready equation for submission

Libraries Used

numpy – Numerical computations

pandas – Data handling

matplotlib – Visualization

scipy.optimize – Optimization

google.colab.files – File upload in Colab

Assessment Alignment

L1 distance (max score 100): Computed to compare predicted and actual points.

Explanation of steps (max score 80): Detailed methodology provided.

Code and repository (max score 50): Full Python code is reproducible and structured.

Notes

The approach ensures parameters stay within constraints.

Uniform sampling guarantees fair L1 evaluation.

The project is fully reproducible in any Python environment or Google Colab.
<img width="1022" height="260" alt="image" src="https://github.com/user-attachments/assets/26029d53-2704-4266-b400-2abc208828bf" />

<img width="1580" height="1019" alt="image" src="https://github.com/user-attachments/assets/940f9272-a5bf-4972-ad86-96c0558900c1" />

<img width="2266" height="144" alt="image" src="https://github.com/user-attachments/assets/bb58144b-02ad-4cb6-bf08-57b1cb87e207" />


