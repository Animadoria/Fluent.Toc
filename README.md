# Fluent.TOC
Interim base TOC client for C#, will replace with a better client from scratch when I have time™.

Fluent.Toc is a .NET component written in C# for communicating with AOL's Instant Messenger (AIM) service. Initially ported from JavaTOC, Fluent.Toc has been extended with more features and redesigned as a .NET API. Fluent.Toc is released under the LGPL.

Additional Information on the TOC Protocol
 - https://wiki.nina.chat/wiki/Protocols/TOC

0.3 Release Features

 - TOC 2.0 Support.

0.2 Release Features

 - Send and receive instant messages.
 - Retrieval and configuration of buddy lists.
 - Warn, permit and deny buddies.
 - Idle and away notification.
 - Password change.
 - Uses simple events for notifications.
 - Message throttling.

Send Message Example

```cs
 TocClient tc = new TocClient();
 tc.SignOn("myscreenname","password");
 tc.Send("mybuddy","Hello!");
 tc.SignOff();
```

Receive Message Example

```cs
  TocClient tc = new TocClient();
  tc.Message += new MessageEventHandler(OnMessage);
  tc.SignOn("myscreenname","password");
  tc.StartListening();
  ...
  protected void  OnMessage(object sender, MessageEventArgs e){
    WriteLine("{0}: {1}",e.From, e.Message);
  }
```


