Download Link: https://assignmentchef.com/product/solved-ece30862-homework-8-a-mapping-app-and-an-alarm-app
<br>
You will complete a program.  The class diagram is given on the next page.  What needs to be done for each class is then explained.  There are partial implementations of some classes, and the main function is provided.

The program simulates two phone apps – a mapping app and an alarm app.  Both apps register with the gps service (the GPS class) and are notified of new GPS locations.  The mapping app prints out the new location, and the alarm app sounds an alarm if the device has moved to far.

What to do for each class

<strong>Subject.h:</strong>

read the comment in Subject.h

<strong>Observer.h: </strong>Read the comment in Observer.h

<strong>GPS.h: </strong>

Declare the class according to the descriptor on the previous page. x and y are the current x and y coordinates. obs is an array of Observer pointers size is the size of the obs array idx is the next element to be written in the obs array

<strong>GPS.cpp:</strong>

<em>GPS::GPS(int s): </em>

Initialize x and y to 0.0.  Initialize size to s.  initialize idx to 0.  Do all initializations in the initializer list.   The obs array allocation is provided.

<em>GPS::~GPS:</em>  Free the storage for obs.  This has been provided

<em>GPS::subscribe(Observer* o)</em>

Add o to the next entry in the obs array if there is space, and print an error if there is not space.  Update idx.

<em>void GPS::update(double xx, double yy); </em>Set x and y to xx and yy, call notify( )

<em>void GPS::notify( )</em>

For each Observer in obs, call the Observer’s notify function, passing it the value of the GPS object’s x and y.

<strong>Map.h:</strong>

Declare the class according to the descriptor on the previous page.

<strong>Map.cpp:</strong>

<em>Map::Map(Subject* s): </em>

Subscribe to the subject s by passing a pointer to this Map object.

<em>Map::~Map:</em> given

<em>void Map::notify(double x, double y) </em>Print out the new location on the map

<table width="806">

 <tbody>

  <tr>

   <td width="662">What to do for each class</td>

  </tr>

 </tbody>

</table>

<strong>Alarm.h:</strong>

Declare the class according to the descriptor on the previous page

The alarm class issues an alarm if the coordinates change too much.

X and y are the initial coordinates.  SoundAlarm is how much movement is too much.  Id is an integer id of this alarm.

<strong>Alarm.cpp</strong>

<em>Alarm::Alarm(Subject * s, int i, double xx, double yy, double alarm)</em>:

Initialize id to I, x to xx, y to yy, soundAlarm to alarm using an initializer list. Subscribe to subject s using s’s subscribe function.

<em>Alarm::~Alarm::</em> provided

<em>Void Alarm::notify(double xx, double yy):</em>

Find the distance from the point (xx,yy) to the object’s (x,y).  If the distance is greater than soundAlarm, print out an alarm.  Otherwise do nothing.

The C++ sqrt function can be used by including cmath and invoking with with std::sqrt.  You do not need to use -lm as an option on your compile.

<strong><em>Main.cpp:</em></strong> it is provided The output from my program is

obs full, size: 3, idx: 3 new map location: (1, 1) Alarm1 Sounded!  Moved 1.41421 meters new map location: (4, 4)

Alarm1 Sounded!  Moved 5.65685 meters

Alarm2 Sounded!  Moved 4.24264 meters