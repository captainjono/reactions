<b># reactions</b>
<i>a little foundation for the days of writing highly specialised inter-connected services. </i> 

<b>* fluent</b>
<b>* micro </b>
<b>* functional</b>
<b>* Rxactive</b>


By embracing rx, and helping allviate backpressure in a variety of situations, you can be comfortable that your technology choice is backed by a passionate group of enthustists who hate getting called in on weekends just because of some wild storm! ;)


<b>#Fluent first?</b>
Lets face it, your program is your documentation. Edit it while you write it.

<b>#Rxactors</b>
With event sourcing at their core, these usiverses host your actors <i>input</i> and <i>output</i> streams. 

<b>#Events</b>
EventManagers connect your universes to the outside world, we provide <i>a few</i> of the more common ones but for those of you feeling adventrous, difer that decision for a bit because we support Orleans & Akka for the hardcore.

<b>#Fluent last</b>
Implement IReactCfg anywhere you want and that actor gets Iets you fiddle with its innerds; how many of those times do you want to ignore half the noise, return <code>pileline.FirstLastDistinct(e=> e.Name)<code> and done with it. 

<b>#Backpressure made easy</b>
<code>pipline.OverflowTo(_azureTable).When(new responseTimeExeeds(200).ms()).ReportAll().ReportsOn(QueueLengthExceed(l => 20), _centralAlertService)</code>

<b>#pkg mgr free</b>
Our design is your design. Its encourged to simply run bare, with a one file download the enouraged form of integration. you can include and split out what you want as your requirements change. Simply diff up the original when you want to upgrade. Or not!
