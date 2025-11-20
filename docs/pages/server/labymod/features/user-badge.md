The `ServerBadgePacket` is a client-bound packet that allows servers to display a badge in the tab list next to the player's name and in the nametag.

![Tablist Badge](../../../../assets/files/serverapi/user-badge-tablist.png)
![Tablist Nametag](../../../../assets/files/serverapi/user-badge-nametag.png)

## Set the Badge Infos

The packet can be sent via the `LabyModProtocol`.

### Via the LabyModProtocol

You can send one or more server badge info to the player.

```java
// Get the LabyModProtocol
LabyModProtocol labyModProtocol = LabyModProtocolService.get().labyModProtocol();

// Create a new ServerBadge
ServerBadge owner = ServerBadge.create(
        1, // The ID of the badge
        new Color(255, 0, 0), // The color of the badge
        "https://example.com/image_owner.png" // The URL of the badge image
);
ServerBadge developer = ServerBadge.create(
        2, // The ID of the badge
        new Color(0, 0, 255), // The color of the badge
        "https://example.com/image_developer.png" // The URL of the badge image
);

// Sent the packet
labyModProtocol.sendPacket(uniqueId, new ServerBadgePacket(owner, developer));
```

## Set the badges for the players.

The packet can be sent via the `LabyModProtocol`.

### Via the LabyModProtocol

???+ danger "Important Note"

    You must first send the ServerBadgePacket before the badges can be displayed next to the players.


Now you can assign the badge to a player, which will then be displayed.

```java
// Get the LabyModProtocol
LabyModProtocol labyModProtocol = LabyModProtocolService.get().labyModProtocol();

// Create a new ServerUserBadge
ServerUserBadge serverUserBadge = ServerUserBadge.create(
        uniqueId, // The UUID of the user
        1 // The ID of the badge
);

// Sent the packets
labyModProtocol.sendPacket(uniqueId, new ServerUserBadgePacket(serverUserBadge));
```
