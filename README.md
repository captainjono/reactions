<h1><b># reactions</b><h1>
<i>a little foundation for the days of writing highly specialised inter-connected services.</i>


<h2><b>* fluent</b><p>
<b>* micro </b><p>
<b>* functional</b><p>
<b>* reactive</b><p>
</h2><p>

By embracing rx, and helping allviate backpressure in a variety of situations, you can be comfortable that your technology choice is backed by a passionate group of enthustists who hate getting called in on weekends just because of some wild storm! </i>event though they are bots inside your computer and does storm in computer land.. ddos maybe?</i>

<b>#Fluent first?</b><p>
Lets face it, your program is your documentation. Edit it while you write it. 

<b>IReacTo\<Reactors\></b><p>
With _IEvent_ sourcing a first order design, these usiverses host your actors <i>input</i> and <i>output</i> streams. Why stop at backend services? I often think those JS guys just rebranded it as Flux when applied to the UI... the aync link? well thats just Subscriptions to your ES DDD data model.. with rewind, playback, shift time, or just support offline and remote sync.  
```c#

this.OnReactionTo<MouseMoved>()
       .SkipWhile(pos => GetMouseState().RightButton.IsPressed()))
       .Do(m => PaintPixel(m.Y, m.Y, Colors.Blue))
       .Until()
       .DisposedBy(_resources);
```
<b>#Events</b><p>
EventManagers (original i know) connect your universes to the outside world, we provide <i>a few</i> of the more common ones but for those of you feeling adventrous, Prototype now, scale up with Orleans & Akka anytime you want.. We provide a set of interfaces that implement patterns as original as IEVentProcessor, IEventPulsar. IEventPublisher...

<b>#...nts drive everything</b>
doubling as your state <i>expressed over time.</i>. The data in your events forms you data model, pinging subscriptions whenever upcates are made is just a bonus side-effect. That is not an endorsement for shared state btw. 
```c#
this.OnReactionTo<UserAttemptingALogin>(e => e.tenant = "a")
       .Do(e => LogAttempt(e.Id))
       .Do(VerifyLoginAttempt)
       .DoWhen(e => SawAttempt(e.Id), e => _publish(new UserLoggedIn(e.Username, e.IP)))
       .CatchWhen<UserLoginFailed>(e => OnWarning("Implement parser later\r\nIPLOG\t{0}\t{1}", e.UserName, e.IP))
       .Until(error => OnError("She shunk the boat: {0}", error))
       .DiposeBy(this);
```

<b>#Build offline fist</b><p>
Once again these events shine their armor by supporting optimistic updates and offline supprt. Which if you think about it for a second could be reason as an overfloww in response to a  

<b>#Bbbbackpressure made easy</b><p>
```c#
pipline.OverflowTo(_azureTable).When(new responseTimeExeeds(200).ms())
```
<b>#Syncing?</b><p>
<i>Yeh i know, events are cool and all but managing them? Organising them?</i> THis is obviously where u should be spending your time thinking, but the intrinic versioning of events is a good start with consisstancy, and we should always be looking at reducing over programs overall complexity while still applying patterns in the right siutation... In this situation, it just defers to disk and assumes the operations are successful

<b>#Typescript / JS bridge</b><p>
POCO ES models converted to the lanuage of your choice allows your domain to follow your implementations, cross platform whatever you choose.

<b>#Fluent last</b><p>
Implement IReactCfg anywhere you want and that actor gets Iets you fiddle with its innerds; how many of those times do you want to ignore half the noise, return 
```c#
pileline.FirstLastDistinct(e => e.Name)
```
and be done with it. 


<b>#so is monitoring</b><p>
```c#
pipeline.ReportsTo(_console)
```
or for the more adventurous
```c#
reactor.ReportsWhen(QueueLengthExceed(l => 20), _centralAlertService).To(_centralLogger)
```

<b>#pkg mgr free</b><p>
Our design is your design. Its encourged to simply run bare, with a one file download the enouraged form of integration. you can include and split out what you want as your requirements change. Simply diff up the original when you want to upgrade. Or not!
