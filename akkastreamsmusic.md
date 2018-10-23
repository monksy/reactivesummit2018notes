# Music with akka streams
-----

Author: 
Twitter:

-----

## Architecture

 - Events to rules (window events, muse events, keyboard events) -> (pitch change, play note, etc)
   - Hub
     - Screen/Music output

 - Akka Streams 
   - Messages to the actor are messages that are joined into the stream

   Source.actorRef


   Extracting by type:

   - Source.collectType[TypeMessage](classTag[MouseWheelRotated]
    - Needs to use classTag https://docs.scala-lang.org/overviews/reflection/typetags-manifests.html
   - Source.tick - Collects at an interval
   - Flow is a node that is being processed
   - Source.merge / combine - bringe sources together
   - toMat -> toMaterialization [of sink)
  - Can run on Raspberry pi
