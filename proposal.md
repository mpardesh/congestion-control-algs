# Proposal

## Description
For my project, I will be working with Dr. Justine Sherry and her Ph.D. student, Ranysha Ware. 

My research project will focus on congestion control algorithms. Congestion control algorithms are implemented to prevent links in the network from being overloaded. These algorithms tell the server how to send packets under different conditions. There are a variety of CCAs in use today, most notably Reno, Cubic, and BBR.

Reno consists of two phases: slow start and congestion avoidance. In the slow start phase, the rate of packet transfer doubles until packet loss occurs. Then, the algorithm transitions into the congestion avoidance phase. In this phase, the window size is halved every time packets are lost, and then the window size is increased by 1 until packets are dropped. This send pattern results in a sawtooth graph.   

One problem with Reno is that this linear increase is quite slow. Cubic solves this problem by using a different increase function. Cubic is similar to Reno, although instead of linearly increasing the window size, it uses a cubic function to increase the window size. Cubic is the default CCA on Linux kernels. 

BBR is the third major algorithm that is in use. BBR was developed by Google and was open sourced when it was found to consume a large amount of bandwidth when sharing links with flows that used other CCAs. 

There are also many lesser known CCAs in use. For example, Akamai uses a mysterious, proprietary algorithm. Recently, Ranysha Ware graphed the behavior of the Akamai algorithm and discovered that it behaves like some known CCAs sometimes, and behaves totally unpredictably at other times. My goal is to discover how this algorithm works. Specifically, I would like to find out how it responds to changes in network traffic and when it uses different send patterns. 

Since Akamai is responsible for routing 15-30% of all web traffic, if its algorithm is unfair, we should know. If I have time, I would like to explore the fairness of the Akamai algorithm. I would like to see how different combinations of algorithms would interact with each other. For example, I would like to see how one flow of the Akamai algorithm would share bandwidth with multiple flows of other algorithms. I would also like to see how two Akamai flows would share the network.  

## Goals 
My 75% goal would be to figure out which events cause Akamai’s congestion control algorithm to behave like TCP Reno. Ranysha has found that Akamai’s algorithm behaves like Reno sometimes, but it is unknown exactly what kind of conditions would cause this behavior and why.    
My 100% goal is to figure out how Akamai’s congestion control algorithm works. In particular, I would like to learn how the algorithm responds to different events such as packet loss and delay. I would also like to learn when the algorithm behaves similarly to known CCAs like Reno.

If I am able to figure out how the Akamai CCA responds to different events, I would like to see how it interacts with other CCAs. My 125% goal would be to explore the fairness of the algorithm and see how Akamai flows share bandwidth with Reno/Cubic/BBR flows. I would also like to see how multiple Akamai flows would share bandwidth. 

## Milestones
By the end of 15-300, I expect to be able to run and debug experiments. To perform a controlled experiment, I will visit a web page and graph the time versus rate of packet transfer. Then I will start changing the conditions by dropping packets at different times and adding a delay to increase the round trip time. Each experiment takes at least a few hours to complete. I will start by replicating a simple experiment that the group has already done.  

By February 1 I would like to reproduce the graph of the Akamai CCA and start experimenting with different traffic patterns. 

From February 15 to March 1 I will continue experimenting with different traffic patterns. 

By March 22, I will start analyzing the experiment results and mapping send patterns to known CCAs. I will try to figure out why the Akamai algorithm would change its behavior based on changes in the network. 

From April 5 to April 19, I plan to continue analyzing experiment results and mapping send patterns to known CCAs. I will form a more solid theory about when the Akamai algorithm behaves like known CCAs.  

By May 3, I will make sure my theory is as specific as possible and tie up any loose ends.

[Milestone 1](https://mpardesh.github.io/congestion-control-algs/milestone_report)

[Milestone 2](https://mpardesh.github.io/congestion-control-algs/milestone_2)

[Milestone 3](https://mpardesh.github.io/congestion-control-algs/milestone_3)

[Milestone 4](https://mpardesh.github.io/congestion-control-algs/milestone_4)

[Milestone 5](https://mpardesh.github.io/congestion-control-algs/milestone_5)

[Milestone 6](https://mpardesh.github.io/congestion-control-algs/milestone_6)

[Milestone 7](https://mpardesh.github.io/congestion-control-algs/milestone_7)

## Literature Search 
I have started reading Computer networking: a top-down approach by Kuros and Ross. I plan to read more about specific congestion control algorithms, especially Reno and any others that the Akamai algorithm may be similar to. I will continue to look for materials when I feel that I am missing information.    

## Resources Needed 
I will be using the servers that Dr. Sherry’s group has already configured. I have access to the group GitHub repository that contains the code that will be relevant to my project.
