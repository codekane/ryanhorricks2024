---
title: "Voice Journal"
description: "What began as an AI-powered voice-journal rapidly evolved into a notebook digitization platform, integrated with the initial sentiment analysis. Python/FastAPI."
summary: "What began as an AI-powered voice-journal rapidly evolved into a notebook digitization platform, integrated with the initial sentiment analysis. Python/FastAPI."
slug: "vouce-journal"
date: "2025-12-20 00:00:00-0700"
lastmod: "2026-09-09"
draft: false
---
This is a project combining both a gift, and a memory of what could be. 
The aim was to improve mental health. 
It became a refuge for the work I'd previously put into Spokebooks, and what I envisioned.

This project was initially borne of an idea related to me at the Entrepreneur meetup in 
Bangkok, by my friend Lulu. She shared with me her idea of a voice journal that used AI to 
analyze sentiment, and through it mental health, and to be able to plot this over time 
using a calendar, and get a fuller understanding not just of how you're doing now, but 
how you've been, the pattern over time, and potentially to provide you with insights, so as 
to help you to better understand your own patterns, and further your growth.

The idea bounced around my head for a while, as I continued to scout Bangkok for opportunities. 
It wasn't until another friend recommended that I get into LiveKit, on account of the freelance 
opportunities that were available to the relevant developers, that I looked back upon this idea, 
and decided to put it into development.

I started by building a simple ChatGPT wrapper. The interface would record the audio as a single 
continguous recording, and then pass it to the OpenAI API for transcription. This part actually 
worked fairly well, and the transcribed recordings I got out of it were quite decent, at a 
very modest cost, in terms of credits. The transcriptions were stored in a database, and then, 
at least initially, I ran it through a sentiment analysis feature that sought to identify 
whether it was positive, negative, or neutral.  

That worked, so I then sought to switch the voice parser from OpenAI, towards LiveKit. The 
problem was that it worked very poorly, and was vastly worse at getting the words from a 
voice note, and so despite it being the initial aim of the project, I opted to rip it out. 

The back-end, at this point, was built using Python, and FastAPI, alongside a simple React 
Front-End.

Now, having invalidated the initial assumption (relating to the value of LiveKit for this 
application), I was reminded not only of the initial idea I was working towards building, 
but also of my own past work. Historically, in the [Spokebooks](https://ryanhorricks.com/portfolio/spokebooks/) project, 
what I'd actually tried to do there was to design a notebook with a grid section, in the hopes 
of being able to effectively transcribe what I'd written on the page, and to convert it into 
text.

So, I went about doing so.

I created the rudiments of a notebook parser, added faculties for uploading files, and 
setup another OpenAI API call to handle transcription. The output turned out to be less than 
stellar, so I then added the ability to edit the transcription, modelling it after a system 
I used working for the Government of Alberta that handled the digitization of records for the 
office of Vital Statistics.

That worked, but it still wasn't perfect. The way that my notes are structured, is that every 
page has a dated timestamp at the top, and potentially carries with it several entries on any 
given page, denoted by either a non-dated timestamp, or else a dated one (should it be a new 
date, or the new date not possible to intuit). Thankfully, my system is quite consistent, so 
I was able to build out logic to somewhat reliably parse the dates, and was able to devise a 
model for the contents of a notebook, with a notebok containing pages containing entries.  

The date parser was imperfect, and so I sought to modify it to detect some of the more 
egregious errors, basing it upon the assumption that I was dealing with a successive number 
of pages, with presumably would carry successive dates. That means that if the next page has a 
time/date stamp that is earlier than the page preceeding it, then it would likely be an error, 
and to thulsy autocorrect it to the most likely case (usually the next day).

Modification were made to the editing system to enable the visualization of an entire page, 
alongside the ability to add, edit, and remove individual entries, while also being able to 
see the raw, scanned image.

This worked. The problem was, at least at this point, that the output from my OCR was very far 
from being perfect. It wasn't the worst thing, but it was quite near. Having provided myself 
with the faculties for editing the results, I set to work creating a clean set of notes from 
the most recent notebook I had on hand... which happened to include a portion involving me going 
through a breakup.

I made it through 80 pages, and honestly, this was the part that took up most of my time. The 
application itself was built using Claude, the OCR was done via OpenAI, however the time spent 
deciphering my own handwriting was immense. Potential improvements include running the scans 
through a filter, similar to what I get when digitizing pages using my iPhone, or in fact to 
modify the importing logic to presume such an input -- at this stage, perfection is not my aim, 
and I've since digitized close to 2 years worth of records.

Unfortunately, I lost all of the work I did put in to those 80 pages, on account of having 
sought to free disk space, and in the process deleted the docker container that hosted the SQL 
instance that all of this was being saved to. Were I to do it again, I'd use Obsidian, or something 
analagous to commit the results into flat files.

It did, nonetheless, functin as-designed. As to the sentiment analysis, I changed between a 
few different versions. To begin with, it was a hard/fast positive or negative sentiment, which 
wasn't ideal, so I changed it to support neutral, and to score it along a gradient, which was an 
improvement. The next iteration sought to assign up to 3 emoji's to each entry, which wound up being 
okay, but not great. I got the idea from my work with the MARA Group, but I think it's a portion 
of the application that could be much more fully fleshed out.

All-in-all, this is something I'm willing to try again, but for the moment I'm hard-pressed to 
call it a priority.
