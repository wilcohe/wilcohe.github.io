---
title: "Linear and Heuristic-based Missile Guidance"
excerpt: "Applications of guidance, navigation, and control for target intercept with a limited-control missile system. <br/> <br/> <img src='/images/kin.png' width='70%'>"
collection: portfolio
---

As a final project for my course on Avionics, Guidance, and Navigation of aerospace vehicles, I was tasked with designing proportional and heuristic controllers for target tracking. Some examples of the results can be found below. 

The linear controllers used a proportional feedback loop based on the target close rate and the horizon angle rate of change. 

- ~Target Close Rate:~ The rate of change of the distance between the pursuer and the target

- ~Horizon Angle Rate of Change:~ The change in the angle between the pursuer and the target, measured to some fixed horizon point

The linear controllers used a proportional multiplier of these two values in order to track our target. Our target for these experiments is a simplified model of an F-16 with constant thrust, and our pursuer is an AMRAAM Sidewinder missile with stepped thrust values. 

<img src="/images/dyn3b.png">

A heuristic-based system was also required to proxy in-the-loop control actions. I chose a "Loft and Glide" heuristic that allows the pursuers limited thrust profile to be boosted by gravity once the thrust is reduced or cuts off. The heuristic is shown below: 

- If the height of the target is greater than that of the pursuer, perform a 1.5g turn opposite the force of gravity until the height of the pursuer is 125% that of the target or the target is within 5km
- Activate a "pursuit" trigger that cannot be turned off
- Once the pursuit trigger is activated, perform proportional guidance based on the Target Close Rate and the Horizon Angle Rate of Change. 

This heursitic allowed for 70% hits, which outperformed the 40% success rate of proportional navigation. Two examples of this heuristic are shown below. 

<img src="/images/s2.png">

<img src="/images/s10.png">