In this project, I implemented several functions related to Bayesian Networks and probabilistic inference. 
First, I implemented the constructBayesNet function in inference.py. 
This function constructs an empty Bayes Net structure based on a given diagram, adding variables and edges according to the specifications provided.

Next, I worked on the joinFactors function in factorOperations.py as part of Question 2. 
This function takes a list of factors and returns a new factor by multiplying the corresponding rows of the input factors. 
It essentially serves as a product rule for factors, allowing the incorporation of probabilities for conditioned variables.

Moving on to Question 3, I implemented the eliminate function in factorOperations.py. 
This function takes a factor and a variable to eliminate, producing a new factor without that variable by summing entries that differ only in the value of the eliminated variable.

In Question 4, I implemented the inferenceByVariableElimination function in inference.py. T
his function answers a probabilistic query using variable elimination, iterating over hidden variables in elimination order and performing join and eliminate operations.

For Question 5a, I filled in missing parts of the DiscreteDistribution class in inference.py. 
Specifically, I implemented the normalize method, which normalizes distribution values to sum to one, and the sample method, which draws samples from the distribution based on proportional values.

In Question 5b, I implemented the getObservationProb method in the InferenceModule base class in inference.py. 
This method calculates the probability of a noisy distance reading given Pacman's position, the ghost's position, and the position of the ghost's jail. 
I handled special cases, such as when the observation is None if and only if the ghost is in jail.

In Question 6, I implemented the observeUpdate method in the ExactInference class, which allowed Pacman to update its belief distribution after receiving a sensor reading. 
This involved iterating over all possible positions on the map and updating the beliefs using the getObservationProb function.

Moving on to Question 7, I implemented the elapseTime method in the ExactInference class. 
This method updated Pacman's belief at each position on the map after one time step, considering the possible legal moves of the ghosts. 
This step incorporated Pacman's knowledge about the ways a ghost may move, such as not passing through walls or moving more than one space in a single time step.

Question 8 took the project further by implementing the chooseAction method in the GreedyBustersAgent class. 
This method made Pacman ready to hunt down ghosts by choosing actions based on the latest belief distributions. 
The strategy involved assuming that each ghost was in its most likely position and moving toward the closest one.

The project then delved into approximate inference methods. 
In Question 9, I implemented the initializeUniformly and getBeliefDistribution functions in the ParticleFilter class. 
These functions focused on initializing particles uniformly across legal positions and converting the list of particles into a DiscreteDistribution object.

Continuing with Question 10, I implemented the observeUpdate method in the ParticleFilter class. 
This method constructed a weight distribution over particles based on observation probabilities, and particles were then resampled accordingly. 
The implementation considered Pacman's position, potential ghost positions, and the jail position.

In Question 11, the elapseTime function in the ParticleFilter class was implemented to advance particles in time. 
This involved constructing a new list of particles corresponding to each existing particle advancing a time step, thereby allowing Pacman to track ghosts more effectively.

The project extended to joint particle filtering in Question 12. 
In this question, I completed the initializeUniformly method in the JointParticleFilter class, which allowed tracking multiple ghosts simultaneously. 
The initialization was consistent with a uniform prior, and the permutations list was shuffled to ensure even placement of particles across the board.

Questions 13 and 14 further enhanced joint particle filtering. 
In Question 13, the observeUpdate method in the JointParticleFilter class was completed. 
This implementation weighted and resampled the entire list of particles based on the observation of all ghost distances. 
Finally, in Question 14, the elapseTime method in the JointParticleFilter class was implemented to resample each particle correctly for the Bayes net, 
considering the positions of all ghosts at the previous time step.

Throughout the project, I used the autograder to ensure the correctness of the implemented functions and visualized the output to observe how belief distributions
evolved and Pacman's ability to track ghosts improved over time.
