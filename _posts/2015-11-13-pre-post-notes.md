---
layout: post
title: "Converting notes: pre-money vs post-money"
date: 2015-11-13
author: robert
category: startup-math
published: false
excerpt: "Who gets diluted and how much is your company is worth."
---

One of the most common questions we receive at Sharewave from early stage companies is about the difference between pre and post-money note conversion. Amazingly this detail is not always included in the terms of a note agreement yet it can make a massive difference to the outcome of a new round of financing. We've explored [the math behind convertible notes](http://blog.sharewave.com/july-22-convertible-notes/) and [the role they play in future rounds](http://blog.sharewave.com/july-10-round-modeling/) in earlier posts, here I'll explain the impact of just this one often missed term.

<h2 style="text-align: left">Who gets diluted?</h2>

This problem really boils down to who gets diluted and how much the company is worth.

<ul>
    <li>
        In a pre-money conversion the notes convert first, and are included as part of your company's value in the pre-money valuation. You may also hear pre-money conversion referred to as "the percentage-ownership method".
    </li>
    <li>
        In a post-money conversion, the incoming series goes first, then the note holders convert increasing the post-money valuation of the company. Because the pre-money value does not include the note holders, it gives a fixed price for the new round shares and so post-money conversion is sometimes (confusingly) referred to as "the pre-money method" when looked at from the perspective of the new investors.
    </li>
</ul>

<h2 style="text-align: left">A concrete example</h2>

Let's work through a simple example to show the effects. We'll use a very basic cap table with just common stock and one convertible round.

<div class="example-block">
    <p>The company has just three securities:</p>

    <ul>
        <li><span>Common</span> An Equity Series with 1,000,000 shares issued</li>
        <li><span>Debt A</span> A Debt series with $1,000,000 invested at a 20% discount.</li>
    </ul>

    <p>This company is doing a Series A of $1,000,000 at a pre-money valuation of $4,000,000.</p>
    <img src="/images/initial_prepostround.png">
</div>

<h2 style="text-align: left">Pre-money conversion</h2>
First, let's look at the results if we go for a pre-money note conversion.

<div class="example-block">
    <p>
        We have one $100,000 note at a 20% discount. We take the discount: divide 100,000 by 0.8 giving us a note value of $1,250,000. This lowers the effective pre-money valuation to $2,750,000 and dividing that valuation by the number of outstanding shares we get a price per share of $2.75.
    </p>

    <p>
        The debt holder therefore gets 454,545 shares for their note and the new series investors get 363,636 shares for their $1M. As you can see below, the new series get their full 20% and all the dilution hits the stakeholders who existed prior to the new investment round.
    </p>

    <img src="/images/final_premoneyround.png">
</div>

<h2 style="text-align: left">Post-money conversion</h2>
Now let's do exactly the same thing except convert the note in post-money.

<div class="example-block">
    <p>
        The pre-money valuation is fixed, so the incoming investors purchase their shares at $4 each. This gives them 250,000 shares and 20% of the company.
    </p>

    <p>
        However the notes then convert. They get the $4 price per share at a 20% discount, giving them 312,500 shares which dilutes all the existing stakeholders including the new series investors. However using this method the implied post-money valuation of the company is not $5M but $6.25M so even though the new series investors hold a smaller percentage of the company the implied value of their shares is the same.
    </p>

    <img src="/images/final_postmoneyround.png">
</div>

<br>
This difference is not to be sniffed at, in this example using identical numbers the founders ended up with 55% or 64% of the company depending on the method used. This isn't a right/wrong issue, both conversions are totally valid, but it's definitely worth being aware of the impact before you sign your note agreement not when you're about to close your series A!
