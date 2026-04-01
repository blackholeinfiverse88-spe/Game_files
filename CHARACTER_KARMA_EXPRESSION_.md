1. Objective

Apply and validate Karma-based behavioral expression using live gameplay.

This phase ensures:
Characters express personality through movement and combat behavior
Clear differentiation between Karma types
No gameplay stat changes


2.Observations

From gameplay testing:

Working Well:
Combat system is stable (from Phase 2)
Attack readability is clear
Animations and VFX are already synchronized
Units engage targets correctly
Primary Issue Identified
Characters initially felt:
Mechanically correct
But behaviorally similar

Solution: Introduce Karma-driven behavior variance

3. Karma Expression Implementation
A. Aggressive Karma
Gameplay Behavior Observed
Units move toward enemies reliably
Engagement happens correctly but lacked intensity
Adjustments Applied:
Increased forward movement bias
Reduced delay between:
Detection → movement
Movement → attack
Limited retreat behavior
Result in Gameplay
Units:
Rush targets immediately
Stay engaged continuously
Rarely disengage
Validation:

 Clear offensive identity
 Feels dominant in frontline

B. Disciplined Karma
Gameplay Behavior Observed
Units engage correctly
But spacing and control were inconsistent
Adjustments Applied
Introduced:
Preferred combat distance
Controlled stop-and-attack logic
Added slight decision delay for clarity
Result in Gameplay
Units:
Maintain spacing
Reposition before attacking
Avoid unnecessary forward push
Validation:

 Feels strategic and controlled
 Clear contrast vs aggressive units

C. Risk-Based Karma
Gameplay Behavior Observed
Movement patterns were predictable
Combat timing felt uniform
Adjustments Applied
Introduced controlled randomness:
Slight path deviation
Variable attack timing
Occasional overcommit or hesitation
Result in Gameplay
Units:
Move unpredictably
Break rhythm during combat
Occasionally take risky engagements

Validation

 Feels dynamic and less robotic
 No gameplay-breaking behavior

4. Behavior & Animation Sync 
Observed Issues
Minor mismatch between:
Movement stop → attack start
AI decision → animation trigger
Fixes Applied
Synced:
AI state transitions with animation states
Attack timing windows
Adjusted animation entry/exit frames

Result:

 Smooth transitions
 No visible desync
 Behavior matches visual intent

5. System Integration
Confirmed in Gameplay
No stat differences across Karma types
No impact on:
Damage
Health
Attack speed
Layer Integration

Karma expression successfully overlays:

AI logic
Navigation
Combat timing

Without affecting:

Pathfinding
Targeting
Combat systems

6. Final Verification Checklist
 No stat changes applied
 Karma visible through movement alone
 Aggressive = forward pressure confirmed
 Disciplined = spacing & control confirmed
 Risk = unpredictable but stable
 AI and animation synchronized
 No gameplay instability

8. Final Outcome

After applying Karma Expression:
Characters feel distinct in personality
Combat is less robotic and more dynamic
Player can identify behavior without UI cues

9. Conclusion

The Karma Expression Layer is successfully implemented and gameplay-validated.

It delivers:
Behavioral identity
Visual clarity
System stability

Without impacting:
Balance
Core mechanics
