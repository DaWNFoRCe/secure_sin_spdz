# secure_sin_spdz
Implements the Task 2 (secure sin(x) for a fix point) and is designed to see how I manage basic coding and the documentation on SPDZ.


## Task 2: 

This is to test how well you can code using the SPDZ subsystem.
See the attached draft document. It is a draft, so it could contain
bugs. We would like an implementation of the sin(x) function
for FIXED POINT x.

## Resolution:
The solution is a standalone .mpc file that strictly follows the logic presented by the SPDZ documentation provided. As backup material, I have also followed [1] and [2] ([1] and [2] are basically the same). The sin functionality was implemented on the file:

       -ssin.mpc (task 2.)
       
As requested, this is a generic implementation of ssin and contains a call and printing code for single fix point parameter that is written directly in the code. The method places the input (angle in radians) in-between \[0,pi/2). From that moment on the algorithm evaluates the polynomial AS INDICATED and returns an sfix value containing the sin of x. 

## Specification:
   
   - I made use of existing functionality currently present at the SPDZ repo.
   
   - Although papers such as [1] and [2] indicate the method could use PreMul functionality they are clear on mentioning that current state of the art only addresses the case where all inputs are integers smaller than p. They suggest the idea of what could be such a mechanism for fix point operations. This could be further discussed and added if requested.
   
   - The functionality is given in the form of a function, that can be called by the body of any program. Indeed, for my example, you just need to (on the same file) edit the function call and send any angle that you might want to calculate. 
    
    
##Instructions: 
    
    1. Compile the exercise: 
    
          .. `./compile.py ssin`
    
    2. Run the code following the instructions provided by SPDZ e.g.:
        
          .. `Scripts/run-online.sh ssin`
    
    3. In case you want to change the agle edit: 
             `angle= sfix(your_angle)`
        
You can reach me for questions at any time

[1]. Bayatbabolghani, Fattaneh, et al. "Secure Fingerprint Alignment and Matching Protocols." arXiv preprint arXiv:1702.03379 (2017).
[2]. Bayatbabolghani, Fattaneh, et al. "Poster: Secure Computations of Trigonometric and Inverse Trigonometric Functions."

