---
layout: post
title: "Converting notes in pre vs post money"
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
        In a pre-money conversion the notes convert first, lowering the effective pre-money valuation. Then the incoming series gets their full expected percentage of the company at the agreed pre-money valuation diluting everyone including the newly converted convertible note holders.
    </li>
    <li>
        In a post-money conversion, the incoming series goes first, then the note holders convert, diluting out everyone including the new series investors, but increasing the post-money valuation of the company.
    </li>
</ul>

<h2 style="text-align: left">A concrete example</h2>

I hope that makes sense in the abstract, but let's work through a simple example to show the effects. We'll use the same basic cap table we used in [our earlier post on round modeling](http://blog.sharewave.com/july-10-round-modeling/) so if you've got any questions about the round model more generally do check that out first.

<div class="example-block">
    <p>The company has just three securities:</p>

    <ul>
        <li><span>Common</span> An Equity Series with 90,000 shares issued</li>
        <li><span>Options</span> An options series with 10,000 authorized, 5,000 issued</li>
        <li><span>Debt A</span> A Debt series with $100,000 invested at a 20% discount.</li>
    </ul>

    <p>This company is doing a Series A of $1,000,000 at a pre-money valuation of $4,000,000.</p>
    <img src="/images/initial-round.png">
</div>

<h2 style="text-align: left">Pre-money conversion</h2>
First let's look at the results if we go for a pre-money note conversion (also known as the percentage-ownership method).

<div class="example-block">
    <p>
        We have one $100,000 note at a 20% discount. We take the discount: divide 100,000 by 0.8 giving us a note value of $125,000. This lowers the effective pre-money valuation to $3,875,000 and dividing that valuation by the number of outstanding shares we get a price per share of $38.75.
    </p>

    <p>
        The debt holder therefore gets 3,226 shares for their note and the new series investors get 25,806 shares for their $1M. As you can see below, the new series get their full 20% and all the dilution hits the stakeholders who existed prior to the new investment round.
    </p>

    <img src="/images/final_premoneyround.png">
</div>

<h2 style="text-align: left">Post-money conversion</h2>
Now let's do exactly the same thing except convert the note in post-money. One quirk worth mentioning here is that this post-money note conversion is sometimes confusingly called the "pre-money method". This is because the pre-money value is fixed and all the numbers are calculated from it.

<div class="example-block">
    <p>
        The pre-money valuation is fixed, so the incoming investors purchase their shares at $40 each. This gives them 25,000 shares and 20% of the company.
    </p>

    <p>
        However the notes then convert. They get the $40 price per share at a 20% discount, giving them 3,125 shares which dilutes all the existing stakeholders including the new series investors. However using this method the implied post-money valuation of the company is not $10M but $10.125M so even though the new series investors hold a smaller percentage of the company the implied value of their shares is the same.
    </p>

    <img src="/images/final_postmoneyround.png">
</div>

<br>
As you can see, even with a relatively small convertible note this difference is not to be sniffed at. Given a much larger convertible note round the difference to all involved (especially the founders) can be very large indeed. This isn't a right/wrong issue, both conversions are totally valid, but it's definitely worth being aware of the impact before you sign your note agreement not when you're about to close your series A!