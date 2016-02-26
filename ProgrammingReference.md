Each simulation is in this form:
  * Officer1, Direction1, Time1, Officer2, Direction2, Time2,...
  * All spaces are ignored.

Officer: 2- or 3-letter abbreviation of the officer.
  * (MC, SC, JC, Ch, Sen, Scr,...)

Direction: A list of steps the officer takes.
  * For instance, JKVZX.
  * There are special steps as well:
    * -AT-X-
      * Positions the officer at the given point.
    * -AT\_S-U-, AT\_NW-U-, etc
      * Positions the officer(s) next to the given point.
      * S, NW, etc specifies where the officer goes.
      * Example: -AT\_S-U- puts the officer south of point U.
    * -AT\_E-MC-
      * Positions the officer(s) next to the given officer.
      * In this example, to the east of MC.
    * For the above 3 steps, the 'Officer' field may be 'ALL' to position all officers, or a list of officers separated by a + sign.
      * For instance: MC+SC+JC, -AT-X-, Now
    * -W-MC-, -NE-U-, etc.
      * Moves the officer next to a point on the floor, or next to another officer.
    * -DIAG-U-, -DIAG\_NW-J, -DIAG\_SE-MC-, etc.
      * Moves the officer, diagonally, to a point on the floor, next to a point, or next to an officer.
    * For the special DIAG_and AT_ keywords, you can specify a distance away from the officer or point on the floor:
      * -DIAG\_S-MC+E+100- would specify that the officer should go South of the MC, plus 100 'twips' East of the MC.
  * Time: When the officer moves.
    * Now
      * Immediately
    * Simult
      * Arrive the same time as the previous officer
    * Unsync
      * Start moving now, disregarding the other officers
    * After
      * Start moving after the previous officer arrives
    * To add delays in the simulation, use this special simulation syntax:
      * "All, Delay, 0.5" to delay a half-second
  * Examples:
    * Mar, XZTCEVU, Now, All, Delay, 1.0, Mar, UZX, Now
      * Marshal sees if all present are members or visitors.
    * MC, XZR, Now, Ch, XZ-E-MC-, After, SC, XZE-N-Ch-,Simult, JC, XZ-S-Ch-, Simult
      * MC, SC, JC, Ch going into the shield formation.
      * SC/JC/Ch arrive together after MC is at R.