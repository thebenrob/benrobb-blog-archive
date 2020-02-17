---
id: 59
title: Is Model Driven Architecture Right For Me?
date: 2007-03-20T18:18:01-07:00
author: Ben
layout: post
guid: http://benrobb.com/2007/03/20/is-model-driven-architecture-right-for-me/
permalink: /2007/03/20/is-model-driven-architecture-right-for-me/
dsq_thread_id:
  - "3187663713"
categories:
  - Old Stuff
---
Is represents Part 2 in the MDA series.  In <a href="https://benrobb.com/2007/03/14/model-driven-architecture-part-1/" title="Part 1">part one</a> we talked about what exactly MDA is and what it can do.  In this section, I wanted to talk a little bit more about how if fits in different places.  This isn't meant to be a comprehensive source of information (it's just a blog), but I would like to discuss some of the things I would look at before making the MDA leap.

How much software development does your firm do?  Not all technology firms are involved in software development, and if yours is one of the ones that doesn't do some hardcore development, MDA is probably not your thing.

For development firms, there are major benefits to be realized under certain circumstances.  Richard Blais from Locus Systems Inc. believes that
<blockquote>...software development is not necessarily an art form.  It requires discipline, it requires a process...</blockquote>
He talks about the benefits of using OptimalJ in a <a href="http://www.compuware.com/products/optimalj/1792_ENG_HTML.htm" title="Go this page then click on the Richard Blais video.">short video clip</a>.  I think it does a good job of illustrating benefits for large development companies.  Some of the highlights are:
<ul>
	<li>Solid code generation, good process within the code</li>
	<li>Reuse of code &amp; effort (4-5 of 10 things that have to be done for new applications are already done)</li>
	<li>Shortened SDLC (55% decrease in time to market)</li>
	<li>Empowers software architects and programmers</li>
	<li>One source of a competitive advantage</li>
	<li>44% revenue growth powered by OptimalJ</li>
</ul>
What if you're not running a big development firm, but you're still in the ball game somewhere.  MDA could be a good fit for your business, but it might not be.  How do you know?  Maybe it's a good fit for certain projects and not for others.

Let's take my hypothetical web development business that helps local businesses get themselves up on the web.  Some of them would want to actually sell products online, but others just want to start a web presence.  Some want to handle online scheduling and others just want their information available.  Is MDA a good fit?

These are some of the things I would look at to decide if MDA is a good fit for my little projects.

<strong>Complexity:  </strong>If the business is very complex, or particularly when the data model is complex, MDA begins to become a stronger candidate.  In my mind, MDA can really shine through when you've got complex rules on top of complex data structures.  Even if you're only using it for the first round implementation, a lot of the complexity can be reduced by an MDA product.

<strong>Size:</strong> Again, the bigger the project, the more potential that MDA can knock out a significant amount of the work up front.

<strong>Flexibility:</strong> This is closely related to the next point, but if there is a lot of flexibility required, perhaps MDA is not the greatest candidate.

<strong>Ambiguity:</strong> If the requirements are ambiguous or the client is figuring things out as you go along.  MDA won't be much help here.  Without a fairly completed definition up front, generating code from a model becomes problematic and difficult.  If you run into this problem very often, you might have a little business problem in your own business besides a difficult client relationship to manage.

<strong>Time line:</strong> I suppose this is related to the first two points as well, but on a tight time line, an MDA product of one sort or another can really help you front load the project and more complex routines taken care of at the beginning.  If you use MDA often and consistently, you might find yourself in the enviable position of Locus and have several components of code that you can reuse from project to project.  That doesn't mean that MDA is the only (or even the best) way to reuse code, but the required levels of formality and process make it a much greater likelihood.

<strong>Existing code base:</strong> If you've got an existing code base, in my mind I would tend to swing away from MDA.  Partially (or poorly) implemented projects tend to have less documentation and formality.  In my experience, that doesn't give you enough information up front to go the MDA route.

I think I'll wrap up tonight's post at this point.  In the last and final installment in my MDA series, we'll take a look at OptimalJ more in depth to see some of the specific benefits it (and MDA in general) can offer.