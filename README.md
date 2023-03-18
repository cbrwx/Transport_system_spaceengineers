# Automated Resource Transport System for Space Engineers
This is a script for a Space Engineers ship that can automatically fly between two locations (mining base and main base), collect cargo from a storage container at the mining base, and transport it to the main base. It uses a remote control block (e.g. cockpit or flight seat) as the autopilot, and a connector block to connect to the storage container.

The script uses raycasting to detect obstacles along the way and avoid them. If an obstacle is detected, the ship will fly up by a set distance to avoid it, then continue to the destination.

# Usage
To use this script, follow these steps:

- Add the script to the remote control block of the ship.
- Name the remote control block "Autopilot".
- Name the storage container at the mining base "Mining Base Storage".
- Set the GPS coordinates of the mining base and main base in the FlyToLocation() function. Replace the x, y, and z values with the actual coordinates.
- Launch the ship and wait until it reaches the mining base.
- Run the script by sending an argument "start" to the remote control block.
- The ship will fly to the mining base, connect to the storage container, collect all cargo, fly to the main base, and stop.
# Customization
You can customize the script by adjusting the following parameters:

- locationName: set the name of the location to fly to (default is "Mining Base" or "Main Base").
- distanceFromObstacle: set the distance to fly up if an obstacle is detected (default is 100 meters).
- clearWaypoints: set to true to clear the waypoints before adding new ones (default is false).

# HowtoUse

In the script, there are two places where you need to input the GPS coordinates for the mining base and the main base. You can find the coordinates in-game by creating a GPS marker. Here's how to input the coordinates in the code:

Create a GPS marker for the mining base and the main base in Space Engineers. To do this, open the GPS tab in your in-game menu (default key: K) and click on "New from current position" when you are at each location.

Note down the X, Y, and Z values of the GPS coordinates for both locations.

Replace the placeholder coordinates in the script with the actual coordinates you noted down. Specifically, you need to replace the Vector3D constructors for miningBaseCoordinates and mainBaseCoordinates. The format for the Vector3D constructor is new Vector3D(x, y, z).

For example, let's say the mining base has coordinates (1000, 2000, 3000), and the main base has coordinates (4000, 5000, 6000). Replace the placeholder coordinates in the script like this:
```
private void FlyToMiningBase()
{
    // Replace with the GPS coordinates of the mining base
    Vector3D miningBaseCoordinates = new Vector3D(1000, 2000, 3000);
    // ... rest of the method
}

private void FlyToMainBase()
{
    // Replace with the GPS coordinates of the main base
    Vector3D mainBaseCoordinates = new Vector3D(4000, 5000, 6000);
    // ... rest of the method
}
```
After replacing the coordinates with the actual GPS coordinates from your game world, the script will guide the vehicle to the correct locations.

# Notes
- The script uses the Vector3D class to represent 3D coordinates in Space Engineers.
- The script uses the IMyRemoteControl and IMyCargoContainer interfaces to interact with the remote control block and storage container.
- The script uses the IMyShipConnector interface to connect and disconnect the ship from the storage container.
- The script uses the MyDetectedEntityInfo class to perform raycasting and detect obstacles.
- The script uses the Runtime.UpdateFrequency property to update the script every 10 ticks.
- The script uses the GridTerminalSystem property to access the ship's blocks by name.
- The script assumes that the ship is in a clear space and can fly in a straight line to the destination. Obstacles that are not directly in the way of the ship may not be detected.

If its crashes, its ur own fault!

.cbrwx
