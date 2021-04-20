# T1DMPC
A study in blood glucose control for Type 1 Diabetes Mellitus patients

# Control Examples
## Ideal System
![] (Ideal.gif)
## System with Noise
![](Noise.gif)
## Average measurement Response
![](Average.gif)

## Literature review and Models
### Literature
#### [Reinforcement Learning in Diabetes Blood Glucose Control](https://www-sciencedirect-com.erl.lib.byu.edu/science/article/pii/S0933365718304548?via%3Dihub)
* General framework includes a Glucose sensor which measures every 5 minutes, a control algorithm with no information other than the measurements, and supplied dosage of insulin.
* A broader scope could include information such as food intake, physical activity, infections, and stress level.
* RL does not require labeled training data, but rather looks at cause and effect
    * have to set correct cost function for RL to accurately reflect desires
    * Performance Metrics included Acceptable ranges, , Control Variability grid Analysis, meal disturbance rejection
* AC Learning and Q-Learning were the most popular RL algorithms  

#### Engineering The Artificial Pancreas
 * Challenges for Feedback control
     * Sensor lag is about 5-15 minutes
     * CGM systems have an absolute error of 13-16%
     * Rapidly Responsind Insulin takes about 60-90 Minutes (use two types?)
     * Time Variation fo Human body:
         * Absorbtion Time varies 20-35% (by site?)
         * Insulin sensitivity changes as much as 50% through the day
     * **Overall Error is 24% to 37% with a lag of 70-110 minutes**
     
     

## Models
 * Time Series Numerical model
 * Nonlinear Model with No delay  
 $$\begin{array}{l}
\dot{G}(t)=-P_{G}\left[G(t)-G_{0}+\varepsilon(t)\right]-\mathrm{SI}(t)\left[G(t) Q(t)-G_{0} Q_{0}\right]+K_{2} P_{S}(t) \\
\dot{I}(t)=-\left(n_{T}+n_{I}\right) I(t)+n_{I} Q(t)+\frac{K_{X} U_{S}(t)}{V_{P}} \\
\dot{Q}(t)=-\left(n_{I}+n_{C}\right) Q(t)+n_{I} I(t) \\
\dot{P}_{S}(t)=\frac{P_{X}(t)+P_{C}(t)}{V_{G}}-K_{1} P_{S}(t) \\
\dot{U}_{S}(t)=K_{X}\left[U_{X}(t)-U_{S}(t)\right]
\end{array}$$



## Project Scope
* over different situations, and disturbances, how does the controller respond?
    * give arrays for disturbances of food intake, desired lebels, base metabolic rate, and observe objective function after control.
* Are we varying the Model or the control method?
* how do we simulate the acceptable glucaose range? An interpolated function?
* How are results generalized?

## Simple Project Ideas
* Focus on safety
* Add units of glucose
* ML Recognition of disturbances
* structuring the oobjective functio for optimal results
* Two types of insulin
* more accurate prediction and parameters
* [Stochacity Modeling](https://apmonitor.com/do/index.php/Main/StochasticOptimalControl) 
