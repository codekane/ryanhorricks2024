---
title: "eMotors Direct"
description: "Motiometer - IoT Sensor Project"
summary: "Motiometer - IoT Sensor Project. Work etailed implementing Push Notificatios using a PHP Symfony Back-End, a React Front-End, and a Java Android App that  collectively communicate, and process data collected from a swarm of ESP32 microprocessors."
slug: "emotors-direct"
date: "2023-09-13 00:00:00-0700"
image: main.png
lastmod: "2024-11-19"
---
## Foreword
I joined eMotors in May of 2023, after applying for an Intermediate-Senior Front-End Developer position. This 
was not a concerted application - it was borne of a flurry of applications, itself borne out of utterly dire 
financial straights. However, upon learning about what the work entailed, and after a single interview with 
Andrey, the CTO, I realized that what we were doing was in fact very closely aligned, and I said as much in a 
follow-up e-mail that I sent to Andrey. 

He offered me a position with the company as an Intermediate Full-Stack Developer. I made several mistakes, 
however, before I'd even begun, and I'd like to point these out, as a vehicle for my own growth, as well as 
to provide anyone who might be reading some lessons to take home.

### Negotiation
The first I made was in not negotiating upon the terms of the contract. This is something worthwhile to do with 
every position you're looking to start, because as much as you might like to imagine that, in 6 months, with 
more experience, you'll be suitably rewarded for the improvements in your skills, and alignment with the project, 
this is unlikely to be the case. You're going to wait a year before your circumstances will materially be 
improved, and it's importing that, if you're going to say yes, you're saying yes to something you're genuinely 
excited about - not just now, while you're desperate, but also in 6 months, when you'll be looking at other 
positions, in other companies, and won't necessarily feel some terribly sense of lack, on account of a lack 
of initial negotiations.

#### Salary
The offer I received was fair. The position I applied to was listed as being from $60,000 - $80,000 a year, and 
the range that I provided was from $60,000 - $90,000. They split it in the middle, and that was fair, however 
I could have negotiated a bit harder, and asked for $80,000. In fact, I found myself running broke off of $75,000, 
when my outside pursuits were factored in, and though it seems small, an extra $416.77/mo (before tax) every 
month would have easily been the difference between living comfortably, and feeling like I didn't have enough. 

Unfortunately, there were several points during my employ where my feelings aligned with the latter, making 
this my first mistake.

#### Vacation
The offer that I signed provided me with 2 weeks of vacation per year, with the possibility to work extra 
hours, and bank time if I wanted more. That's "standard", if you're in America, however it's not good enough. 
Two weeks of vacation per year says that you don't deserve to have fun, and that's bollocks.

That being said, the opportunity to bank time was in fact quite reasonable, on account of the Family Values 
that the company upholds. They don't want you to work overtime, or weekends (and in fact, doing so is actively 
discouraged)Two weeks of vacation per year says that you don't deserve to have fun, and that's bollocks.

That being said, the opportunity to bank time was in fact quite reasonable, on account of the Family Values 
that the company upholds. They don't want you to work overtime, or weekends (and in fact, doing so is actively 
discouraged). Those are very positive votes, on the topic of culture, and I commend them for that. Nonetheless, 
my 2nd mistake was in not pushing for 3 weeks of vacation from the outset.

Saying that, I'm fairly sure that number would have gone up after a number of years of service, but that's 
besides the point, unless that number of years of service is no more than one. While this may have been a 
standard contract, that was not enough vacation time for me to live in a manner that I'd consider healthy, 
and regardless of whether everyone else said yes to it, I was mistaken not to ask for what I actually needed.

#### Remote Work
This is perhaps the most egregious mistake of all. The whole I got into tech was to provide myself with the 
faculty to work remotely, and travel while I did it. I was asked, during the interview, if I was looking to 
go into the office, or work remotely, and I sold myself out, and said Hybrid.

I was scared. I desperately needed this job. I was afraid that if I asked for what I actually wanted, that I 
would be rejected, and so I said something that I thought was wanted to hear. I then proceeded to sign a 
contract that obligated me, very specifically, not to live my dream. While I was desperate, that was okay, 
but that desperate didn't last long, and I've found that in very instance in which I've said yese to something 
that fails to meet my needs, the psychological effect is absolutely corrosive on my health, wealth, well-being, 
and happiness.

What's more, what I wanted was in fact quite reasonable (just look at the way that Digital Nomad has entered 
into our public vernacular). On my 2nd day, I spoke to Andrey about it, but even then, I sold myself short, 
and said that despite what I'd claimed in the interview, I was looking to travel abroad, and work remotely 
for a month. He said I just neeeded to talk to him (reasonably man, that he is), however even that wasn't 
entirely true. My journey has now stretched for 3 months, and is unlikely to abate soon, and this is what 
I really wanted to do.

Could I have done it while working here? Had I been honest about what it was I wanted, I truly believe 
that the answer was yes. By failing to ask for it, I allowed a maelstrom to brew within my psychological 
condition which would ultimately lead me to get nothing that I wanted. This has been a recurring theme.


## React Camera Switcher
The first week of the job, I was assigned to add a feature to the React front-end. The way that it initially 
worked was to use the rear-facing camera to scan for a QR Code, which was then used for device provisioning.

The feature request came from the Project Manager. His phone had multiple rear-facing cameras, and he was 
having trouble correctly registering the QR Code. I was tasked with implementing functionality to change between 
the different cameras available on the device.

{{<gallery>}}
  <img src="emotors_camera_switcher_1.png" class="grid-w50" />
  <img src="emotors_camera_switcher_2.png" class="grid-w50" />
{{</gallery>}}

The feature was implemented within the bounds of what's possible - that didn't turn out to be choosing between 
multiple rear-facing cameras. In theory, it should have been - there were multiple cameras on his device, as 
well as on the device I was using to test. Unfortunately, the device I was working on was a Huawei P20 Pro, which 
turned out to present issues, when it comes to addressing those cameras. What I was able to do was to implement 
functionality to switch between the front-facing, and rear-facing cameras. This seemed to be possible to do 
accross a wide swath of different devices, using a fairly standard set of API's.

The feature was successfully delivered, although in retrospect, I'm not sure that it was done so in an 
entirely satisfactory manner. I do recall the desired functionality being technically possible, however it was 
largely limitations borne of hardware that kept it from being implemented. Had I dropped several hundred dollars 
on a new phone, with which to test this niche feature during my first week on the job, it might have been 
possible to implement more fully.

## Upper Bound

## Push Notifications

###  PHP (Symfony) Back-End

#### Documentation

### Android (Java) Mobile App
{{<gallery>}}
  <img src="eMotors_Splash.png" class="grid-w50 md:grid-w33"/>
  <img src="eMotors_Welcome_Back.png" class="grid-w50 md:grid-w33"/>
  <img src="eMotors_Forgot_Password.png" class="grid-w50 md:grid-w33"/>
  <img src="Create_Account_Company_Details.png" class="grid-w50 md:grid-w33" />
  <img src="Create_Account_Details.png" class="grid-w50 md:grid-w33" />
  <img src="Complete_Account_Creation.png" class="grid-w50 md:grid-w33" />
  <img src="Verify_Email.png" class="grid-w50 md:grid-w33" />
{{</gallery>}}

#### Documentation

#### Collaboration

Scope of work included Push Notifications, which were successfully implemented. Given the Android app had no 
faculties for Authentication, I did that too, and I even went a bit too far, and setup Registration.

Behind the scenes, I took a disparate, undocumented codebase worked on primarily by Juniors, and bestowed upon it 
order, patterns, Best Practices, and, get this: Documentation. This was done using Java, implementing the MVVM pattern, with a single-activity, 
many fragments, and JWT for Authentication.

