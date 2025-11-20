The `UpdateLabyModUserIndicatorVisibilityPacket` is a client-bound packet that allows servers to hide the indicator of a player.

## Sending the Packet

The packet can be sent via the `LabyModProtocol`.

### Via the LabyModProtocol

```java
// Get the LabyModProtocol
LabyModProtocol labyModProtocol = LabyModProtocolService.get().labyModProtocol();

// Sent the packet
labyModProtocol.sendPacket(uniqueId, new UpdateLabyModUserIndicatorVisibilityPacket(false));
```