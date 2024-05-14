# Patient Segmentation Cancer
- This project idea is taken from [here](https://www.youtube.com/watch?v=Ur53bjPEPqs)
- The dataset is taken from [here](https://github.com/marshall4471/Cancer_data/tree/main)
- Yet, there was not a description of the dataset.
- I'll use this opportunity to review the PCA and review some tecniques used for clustering analysis.


## PCA (Principal compenent analysis)

### Goal: 
- Given a dataset with k columns, I want to map it to a smaller dimension v such that v < < k;

- Ingredients:
    1. Vector projections
    2. EigenValues & Eigenvectors
    3. Lagrange Multipliers
    4. Derivative of a Matrix
    5.  Covariance Matrix


Let's review briefly these concepts:

1. Vector projections
    Projecting A on B means mainly projecting the magnitude of A on B since the direction is already set;
    This assumption is the one we use to understand why we use always project on the unit vector of a given vector B; 
    Now this make also possible to store less values for representing a given set of vectors; since the unit vector and the magnitude is only needed for storing 1 vector;

    the magnitude alpha can be computed as: alpha = ||A|| * cos (theta) = A dot product B

    - What is the dot product operation?
    (Also called the Inner product)
    - It is an algebraic operation that takes two equal-length sequences of numbers (usually coordinate vectors), and returns a single number
    - Algebraically, the dot product is the sum of the products of the corresponding entries of the two sequences of numbers. 
    - Geometrically, it is the product of the Euclidean magnitudes of the two vectors and the cosine of the angle between them.
    (the Euclidean norm is a measure of magnitude used to define a distance between two points in space) 


2. EigenValues & EigenVectors

    Given a SQUARED matrix A, an EigenVector x is ANY vector which is not equal to 0 such that multipluing A by x gives back some multiple of vector x where that multiplier λ has to be a real number (λ is a eigenvalues for x )

    - Now, let's compute an example: 

        I have a squared matrix A:

            | 0  | 1  |
            | -2 | 3  |

            
      

        Let's figure out its eigenvalues and eigenvectors;

    
    We know an eigenvector has to satisfy the previous definition: A x = λ x


    1. add the identity matrix (we can add it is equivalent to multiply by 1 an equation), now we have A x = λ x = λ IDM x
    2. extract the the following equation: A x - λ ID x = 0
    3. Let's factor the x, ( A - λ ID ) x = 0 
    4. to solve this equation we need to remember that x has to be different from 0
    5. and so it means there is some matrix M = ( A - λ ID ) such that if i compute M x i get 0 and so it means M is not invertible
    6. if M is invertible, its determinant has to be equal to 0 by def
    7. therefore det (M) = 0 = det ( A - λ ID ) 
    8. let's write M in full form:
  
            | 0  | 1  |
            | -2 | 3  |
 
                -
               
            | λ  | 0  |
            | 0  | λ  |


                =

            | -λ  | 1  |
            | -2  | -3 - λ |

    Now we can compute the determinate;
   
    - How? for a 3x3 Matrix:
    - 
    $$
    \begin{vmatrix}
    a & b & c \\
    d & e & f \\
    g & h & i
    \end{vmatrix}
    = aei + bfg + cdh - ceg - bdi - afh
    $$








