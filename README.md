### How to Play
Set the values of the ball’s speed, ball type, bowling side, bat’s speed, and bat’s elevation.
Drag across the screen to set the marker at the point where you want the ball to pitch.
Press the “Throw” button to release the ball.
Swipe in any direction once the ball is in the hit range of the bat to hit it.
Press the “Reset” button to reset the game.

### Features

The ball’s bounce angle depends on the ball’s speed. Higher the speed, higher the bounce.

The ball’s speed after it gets hit by the bat depends on both the bat’s speed and the ball’s incoming speed. A faster ball will have more return speed compared to a slower ball at the same bat hit speed.

The elevation of the ball decides whether the shot will be lofted or grounded.

If a leg spin or off spin ball is delivered, the amount of spin also depends on the ball’s speed. A faster ball spins less compared to a slower one.

### How does it work?

When the ball is thrown:
In the beginning, the ball’s interaction with gravity is disabled. An impulse force is added to the ball with the ball’s speed value in the direction of the marker’s position.

Once it hits the ground, we calculate the bounce direction by negating the Y component of the direction vector and then scaling it up or down based on the ball’s speed and another scalar value. An impulse force is then applied in this new direction using the ball’s speed value.

At this point, gravity is enabled on the ball’s rigidbody (useGravity = true) to make the post-bounce motion look more realistic.

After the player swipes to hit the ball:
The bat’s forward direction is used to calculate the hit direction of the ball. Once the player swipes across the screen, we calculate the swipe angle and update the bat’s rotation to match it.

Then we use the bat’s forward direction to determine the hit direction and send the ball in the opposite direction by adding an impulse force based on the bat’s speed and half of the ball’s speed.

### Note: The bat will not hit the ball if the swipe is not perfectly timed. The bat movements are not fully realistic and are currently simplified for gameplay.

### Future Expansions

# Batsman & Bowler Assets

Replace the placeholder bat with a full batsman character model, including idle, backlift, and follow-through animations.

Add a bowler character who runs in and releases the ball with different bowling actions (fast, spin, etc.).

Sync the ball’s spawn and release timing with the bowler’s hand animation for more realism.

# Ground & Boundary System

Add a proper cricket ground with an inner circle and boundary rope.

Place colliders around the boundary to detect 4s and 6s based on where the ball lands or crosses.

Show visual and UI feedback like “FOUR!”, “SIX!”, or “Caught at boundary” when the ball interacts with these areas.

Optionally add fielding zones or simple fielders near the boundary for future expansion of catches and run-outs.
