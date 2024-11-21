---
title: "eMotors Direct"
description: "Motiometer - IoT Sensor Project"
summary: "Motiometer - IoT Sensor Project. Work etailed implementing Push Notificatios using a PHP Symfony Back-End, a React Front-End, and a Java Android App that  collectively communicate, and process data collected from a swarm of ESP32 microprocessors."
slug: "emotors-direct"
date: "2023-09-13 00:00:00-0700"
image: main.png
lastmod: "2024-11-21"
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


## Camera Switcher
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

### Code Samples

#### React
```javascript
import CameraSwitchIcon from '@mui/icons-material/Cameraswitch'


useEffect(() => {
     const getFacingMode = async () => {
        const devices = await navigator.mediaDevices.enumerateDevices()
        let deviceIds: String[] = new Array()

        devices.forEach((device) => {
            if (device.kind === 'videoinput') {
                deviceIds.push(device.deviceId)
            }
        })
        if (deviceIdList.length === 0) {
            setDeviceIdList(deviceIds)
        }

        if (deviceIds.length === 1) {
            setFacingMode('user')
        } else {
            setFacingMode('environment')
        }
    }
}

const switchFacingMode = async () => {
  if (deviceIdList.length <= 1) {
    return
  }
  if (facingMode == 'user') {
    setFacingMode('environment')
  } else if (facingMode == 'environment') {
    setFacingMode('user')
  }



<>
  <div className='qr-reader-bottom-options p-4'>
    {/* Switch Front/Back Camera */}
    <div>
      <button
        type='button'
        onClick={() => {
          switchFacingMode()
        }}
      >
        <span className='sr-only'>Switch Camera</span>
        <CameraSwitchIcon/>
      </button>
    </div>
  </div>
</>
}
```

#### SASS
```sass
.qr-reader-bottom-options {
  position: fixed;
  bottom: 0;
  left: 0;
  width: 100%;
  z-index: 1;
  //align-items: end;
  justify-content: end;
  display: flex;

  button,
  button:focus {
    position: relative;
    color: #fff;
    svg {
      font-size: 2rem;
    }
  }
}
```

## Upper Bound
Initially, the plan as that I come into the office, and slowly work up to the prospect of being remote. Luckily, 
my 2nd week of employment was the Upper Bound conference, and I had a ticket. Not only that, but Andrey, and 
another developer, Leo, were both going. I sensed that my presence there wasn't exactly planned - that this 
was something awarded as a result of priviledge, and seniority, however I clearly managed to jump the shark.

This was my first foray into AI, and I took a lot of notes. I attended a lot of talks. I made a lot of connections, 
and I learned a great deal about what, exactly, AI is, how it's done, and what you can get out of it.

There were two main directions that I saw it going - academic, and practical. On the academic side, you had 
well-funded teams of students, professors, alongside sponsoring companies who measured their progress based upon 
how effective their model was at playing video games. This is a useful model - it's something a person can 
do, get better at, and play competitively. What I saw was that, at least in the exceptional cases, that these 
models were in fact capable of becoming very, very good at what they were tasked with; even beating humans.

On the practical side, I saw businesses who, after investing substantial quantities of money, and man-power, 
were able to leverage the technologies for practical applications. Given that this was a venture eMotors 
themselves were intending to leverage, I found this to be the more interesting avenue.

### Team Building
We took a break from the conference for half a day, and met up at the office for pizza. Pizza gets a bad rap, 
when it comes to the workplace - I see memes about pizza parties being provided in lieu of adequate compensation, 
or any fungible (monetary) reward. I'll beg to differ here - it was genuinely a pleasure to spend time with 
the rest of the company, get to know them, and to get fed in the process. We had pizza, and wings, and soft 
drinks, and we got to know each other on a level we otherwise wouldn't, on account of the disparate nature 
of our departments.

This is pertinent because, though eMotors Direct was something of a startup, it was grafted on top of the 
existing business - Universal Rewind. The company was founded by Chris Beaton, some 20 years before I 
ever got to become a part of it, and it had continued to grow from there. The original order of the business 
pertained to electric motor repairs, which, if you know anything about motors, can entail rewinding them 
with copper (hence the name). From that business was borne eMotors Direct, the premise of which was to serve 
the primary market, arranging for sales of the motors from their suppliers, and making sales, which would 
then ultimately serve to feed back into the core business of reparing those very motors.

What I did was in fact somewhat isolated from these core businesses - I worked on the tech side, which was 
utterly dwarfed by the number of people working in sales, and what's more, i was working on a new product, 
still in development, and so the number of people I had to speak with, on a day to day basis was but a 
handful.

After pizza, we went to Activate, and we had fun. We split up into teams, were given fobs, and spent the next 
couple of hours working together to accomplish a variety of meaningless, enjoyable feats. Sometimes we tossed 
balls, sometimes we climbed rocks accross a chasm. The most fun that I remember having was akin to playing 
"The Floor is made of Lava" as a child, where we had to navigate through a series of levels, avoiding the 
bad blocks, knocking out the good blocks, all while avoiding certain death, and respecting the time limit. 

We went hard. I was on a team with Jill Wallace, and we kept going until we were all out of breath, trying, 
and trying again, and doing our damnedest to beat every level they threw at us. I won't pretend that we 
succeeded, however this game was our very last of the day, and on some level, we all knew that, and enjoyed 
it to it's very fullest.

These are memories I hold fondly.
### The Party
I didn't actually wind up seeing Andrey and Leo for most of the conference - I was late in my application 
for the talent bursary, and by the time I went to book my sessions, the main sessions for several of the 
talks were already full, leading me to join the televised "side-session". We ran into each other at a few 
different moments, however I found our footprints to be quite distinct. They went together, as representatives 
of the company, while I walked alone, attending what I most saw fit, and interacting with a great many more.

Perhaps the choisest of the interactions came about during the party. If you've ever attended a conference 
before, you'll know they throw sick parties, and Upper Bound was no different. I didn't run into my 
co-workers there - Andrey had a family, and Leo had a girlfriend (wife???). I am... untroubled by these 
considerations, and even if I was, I'm still not one to say no to a party.

The venue was sick. They provided a free drink, to which I imbibed, and I enjoyed the wonderful opportunity 
that is talking to the next generation of developers; the students, still deciding on what it is they're 
looking to do with their lives, and careers. I shared accumulated wisdom, concerning the difference between 
going corporate versus a startup, and talked about my own venture. The choicest question I remember being 
asked was hwo I managed to balance working a full-time job, alongside working on my own project/company.

I'm not sure that I really did. There were many days where I got 4 hours of sleep, having worked for 8 hours 
working my job, hitting every networking event that existed, and then working to realize my own vision, on 
top of it all. There's a reason I was at the party, but none of my co-workers were... they had someone to 
go home to.

#### Kobold Completions
One of the [talks](https://www.youtube.com/watch?v=Ilza3KuRHKg) that I attended, concerning the practical applications of AI was given by David Cooper, of 
Kobold Completions. I just so happened to run into him at the party, playing a game of Pong. I introduced 
myself, and upon finding out who he was, told him how great it was to hear from someone who'd practically 
applied AI to solve an actual business case. We talked for a while, and he expressed an openness to connect 
further, having expressed that the company I worked for was likewise interested in the applications of 
machine learning/AI.

Why does this stick out? Because sometimes the best way to get to know someone isn't in the office. Sometimes 
the best way to connect is when everyone's had a couple drinks, inhibitions are lowered, and mingling comes 
more freely. A lot of people in tech are not so inclined - they might not feel themselves suited to speak 
with customers, nevermind the speakers at a conference. I do not suffer this problem, being something of a 
brave butterfly in the circles I run in.

## Authentication
With the fun & games out of the way, it was time to get to work. The system we used was Scrum, and the task I 
was given was to implement Push Notifications.

The problem with that is that, upon investigation of the Android app, I realized that it actually made no 
efforts to authenticate users. A bulk of the functionality was made available in the form of a WebView, 
and it was possible to log in there, however this wasn't actually integrated into the functionality of the 
app itself, but rather served to re-use the existing functionality of the React front-end for the main site.

So, to me, the logical next step was to implement Authentication within the Android App itself. I gave an 
initial quote of 2 weeks, based upon my prior experience committing to unreasonable deadlines, while working 
in a new framework. It turned out that, while that estimate may have been reasonable when working on a 
Python/Django/Angular WebApp, it was much less accurate when working in Java on an Android app.

### Android
The initial, and in fact the only required feature set was to be able to log in to the application. The 
back-end was already making use of JWT authentication token, for communication with the back-end, and I was 
able to re-use the bulk of this logic to authenticate the mobile app using the same mechanisms.

{{<gallery>}}
  <img src="eMotors_Splash.png" class="grid-w50 md:grid-w33"/>
  <img src="eMotors_Welcome_Back.png" class="grid-w50 md:grid-w33"/>
  <img src="eMotors_Forgot_Password.png" class="grid-w50 md:grid-w33"/>
{{</gallery>}}


## Registration
Once the initial logic was done to enable authentication, I 

{{<gallery>}}
  <img src="Create_Account_Company_Details.png" class="grid-w50" />
  <img src="Create_Account_Details.png" class="grid-w50" />
  <img src="Complete_Account_Creation.png" class="grid-w50" />
  <img src="Verify_Email.png" class="grid-w50" />
{{</gallery>}}


## Push Notifications

###  PHP (Symfony) Back-End

#### Documentation

#### Automation

#### Testing

#### Documentation

#### Collaboration

Scope of work included Push Notifications, which were successfully implemented. Given the Android app had no 
faculties for Authentication, I did that too, and I even went a bit too far, and setup Registration.

Behind the scenes, I took a disparate, undocumented codebase worked on primarily by Juniors, and bestowed upon it 
order, patterns, Best Practices, and, get this: Documentation. This was done using Java, implementing the MVVM pattern, with a single-activity, 
many fragments, and JWT for Authentication.

