---
name: email-automation
title: Email Marketing Automation
description: Complete email automation sequences including welcome, abandoned cart, post-purchase, re-engagement, and win-back campaigns
version: 1.0.0
tags: [email, marketing, automation, lifecycle, retention]
---

# Email Marketing Automation

## Purpose

This skill provides complete, ready-to-deploy email automation sequences for ecommerce and B2B businesses. Each sequence includes actual email templates with subject lines, preview text, body content, and timing recommendations.

**Use this skill when:**
- Setting up a new email marketing platform
- Improving existing automation sequences
- Onboarding new customers systematically
- Recovering abandoned carts
- Re-engaging dormant customers
- Building post-purchase relationships

**GTSE Context:** For trade and industrial supply companies, email automation serves both B2C (DIY/consumer) and B2B (trade account) customers. Templates include variations for both audiences where relevant.

## Inputs

- `company_name`: Your business name (e.g., "GTSE")
- `website_url`: Main website URL
- `support_email`: Customer support email address
- `support_phone`: Customer support phone number
- `sender_name`: From name for emails (e.g., "Sarah from GTSE")
- `product_category`: Primary product focus for personalization
- `esp_platform`: Email service provider (Klaviyo, Mailchimp, etc.)

## Prerequisites

Before implementing these sequences:

1. **Email Platform Setup**
   - ESP account configured (Klaviyo, Mailchimp, ActiveCampaign, etc.)
   - Domain authenticated (SPF, DKIM, DMARC)
   - Sending reputation established
   - Unsubscribe mechanisms working

2. **Technical Integration**
   - Website tracking pixel installed
   - E-commerce platform connected
   - Customer data syncing properly
   - Events triggering correctly

3. **Legal Compliance**
   - GDPR/PECR compliant consent collection
   - Privacy policy updated
   - Unsubscribe links working
   - Clear sender identification

4. **Content Assets**
   - Logo and brand images
   - Product images
   - Social proof (reviews, testimonials)
   - Product recommendations algorithm (or manual curation)

---

## Procedure

### Sequence 1: Welcome Series (5 Emails)

**What:** Introduce new subscribers to your brand, build trust, and drive first purchase.

**Trigger:** Newsletter signup or account creation (no purchase yet)

**How:**

#### Email 1: The Welcome (Immediate)

**Timing:** Send immediately upon signup

**Subject Line Options:**
- "Welcome to GTSE - Here's 10% off your first order"
- "You're in! Here's your exclusive welcome discount"
- "Welcome to the family, [First Name] 👋"

**Preview Text:** "Your 10% discount code inside + what to expect from us"

**Email Template:**

```html
Subject: Welcome to GTSE - Here's 10% off your first order
Preview: Your 10% discount code inside + what to expect from us

---

Hi [First Name],

Welcome to GTSE! 

We're thrilled you've joined our community of DIY enthusiasts and trade professionals across the UK.

Here's your exclusive welcome gift:

┌─────────────────────────────────────┐
│     10% OFF YOUR FIRST ORDER        │
│                                     │
│     Use code: WELCOME10             │
│     Valid for 14 days               │
│                                     │
│     [SHOP NOW →]                    │
└─────────────────────────────────────┘

WHAT MAKES GTSE DIFFERENT?

✓ Family-run UK business since 2012
✓ Trade-quality products at fair prices  
✓ Free delivery on orders over £45
✓ Real humans answering your questions

WHAT TO EXPECT FROM US:
- Useful tips and how-to guides
- First look at new products
- Exclusive subscriber-only offers
- Industry insights and trends

We typically send 2-3 emails per week. Not your thing? You can update your preferences or unsubscribe anytime.

Got questions? Hit reply - I read every email.

Cheers,
Sarah
Customer Success Manager, GTSE

P.S. Your WELCOME10 code expires in 14 days. Don't miss out!

---

[SOCIAL ICONS: Facebook | Instagram | YouTube]

GTSE Ltd | 123 Business Street, London | support@gtse.co.uk | 0800 123 4567

Unsubscribe | Update Preferences | View in Browser
```

**Design Notes:**
- Large, clear discount code box
- Brand color header
- Mobile-optimized single column
- One clear CTA button

---

#### Email 2: Brand Story (Day 2)

**Timing:** 2 days after signup

**Subject Line Options:**
- "The GTSE story (and why we do things differently)"
- "From garage to warehouse - our journey"
- "Why thousands of tradespeople trust GTSE"

**Preview Text:** "How a family obsession with quality became a business"

**Email Template:**

```html
Subject: The GTSE story (and why we do things differently)
Preview: How a family obsession with quality became a business

---

Hi [First Name],

Yesterday you joined the GTSE family. Today, I wanted to share why we started this company.

OUR STORY

In 2012, our founder was a sparky (electrician) who got tired of two things:

1. Rubbish quality products that failed on the job
2. Being treated like a number by big suppliers

So he started GTSE - first from his garage, then a small unit, now a proper warehouse serving thousands of customers across the UK.

[IMAGE: Team photo or warehouse shot]

WHAT WE BELIEVE

🔧 QUALITY MATTERS
Every product we sell, we've tested ourselves. If we wouldn't use it on a job, we don't sell it.

💷 FAIR PRICING
Trade quality doesn't mean trade markup. We keep prices honest because we remember what it's like to pay the bills.

🤝 REAL SERVICE
Phone rings? A person answers. Email us? You'll hear back today. No chatbots, no runaround.

TODAY, WE SERVE:

• 15,000+ trade and DIY customers
• Electricians, plumbers, builders, and hobbyists
• Next-day delivery across the UK
• 4.8★ average rating from 3,000+ reviews

STILL GOT THAT 10% OFF

Your WELCOME10 code is waiting. Why not grab those cable ties, screws, or tools you've been meaning to stock up on?

[SHOP NOW - 10% OFF →]

Questions about what we do? Hit reply. I'm always happy to chat.

Cheers,
Sarah

---

[Footer]
```

**Design Notes:**
- Conversational, story-driven tone
- Include authentic image (team, warehouse)
- Reinforce welcome discount
- Build trust and relatability

---

#### Email 3: Social Proof (Day 5)

**Timing:** 5 days after signup

**Subject Line Options:**
- "Don't just take our word for it..."
- "Here's what other [City] customers say"
- "Why 15,000+ customers choose GTSE"

**Preview Text:** "Real reviews from real customers (we don't edit these)"

**Email Template:**

```html
Subject: Don't just take our word for it...
Preview: Real reviews from real customers (we don't edit these)

---

Hi [First Name],

When we say we're different, we know you might be sceptical. 

Fair enough. Actions speak louder than words.

So here's what actual customers are saying:

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

"Best cable ties I've ever used. Heavy duty and the price is bang on. Will be ordering again."
⭐⭐⭐⭐⭐ - Dave T., Electrician, Manchester
Verified Purchase - Cable Ties 300mm Black

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

"Ordered Thursday evening, arrived Saturday morning. Exactly as described and well packaged."
⭐⭐⭐⭐⭐ - Michelle K., DIY Enthusiast, Bristol
Verified Purchase - Wood Screw Assortment Box

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

"Finally a supplier who answers the phone! Had a question about sizing, they sorted it in 5 mins."
⭐⭐⭐⭐⭐ - Steve P., Property Maintenance, Leeds
Verified Purchase - Mixed Fixings Set

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

THE NUMBERS DON'T LIE:

📦 50,000+ orders delivered
⭐ 4.8/5 average rating
🔄 98% would buy again
📞 <2 min average call answer time

READY TO SEE FOR YOURSELF?

Your 10% welcome discount is still active. Give us a try - if we don't blow your socks off, we'll make it right.

[BROWSE BEST SELLERS →]

Code: WELCOME10 (expires in [X] days)

See you soon,
Sarah

---

[Footer]
```

**Design Notes:**
- Real review screenshots if possible
- Specific names and locations add credibility
- Stats box for quick scanning
- Urgency on expiring discount

---

#### Email 4: Best Sellers / Value Email (Day 8)

**Timing:** 8 days after signup

**Subject Line Options:**
- "Our 5 most popular products (and why)"
- "What's flying off our shelves this month"
- "[First Name], these are our customer favourites"

**Preview Text:** "Discover what other customers can't stop ordering"

**Email Template:**

```html
Subject: Our 5 most popular products (and why)
Preview: Discover what other customers can't stop ordering

---

Hi [First Name],

Curious what other customers are buying? 

Here are our top 5 best-sellers this month - and why they're so popular:

---

#1 HEAVY DUTY CABLE TIES 300mm BLACK (100 Pack)
[PRODUCT IMAGE]
⭐⭐⭐⭐⭐ (847 reviews)
£8.99

WHY CUSTOMERS LOVE IT:
• 22kg tensile strength
• UV resistant for outdoor use
• Professional quality at DIY prices

"These are the real deal. Use them on every job." - Mike T.

[ADD TO CART →]

---

#2 WOOD SCREW ASSORTMENT (500 pieces)
[PRODUCT IMAGE]
⭐⭐⭐⭐⭐ (412 reviews)
£19.99

WHY CUSTOMERS LOVE IT:
• 10 most popular sizes in one box
• Pozi countersunk heads
• Storage case included

"Finally, one box that covers everything." - Sarah L.

[ADD TO CART →]

---

#3 PROFESSIONAL ELECTRICIAN SCREWDRIVER SET
[PRODUCT IMAGE]
⭐⭐⭐⭐⭐ (328 reviews)
£34.99

WHY CUSTOMERS LOVE IT:
• VDE rated to 1000V
• Comfort grip handles
• Lifetime warranty

"Best value VDE set I've found." - Chris B.

[ADD TO CART →]

---

#4 SELF-ADHESIVE CABLE CLIPS (100 Pack)
[PRODUCT IMAGE]
⭐⭐⭐⭐⭐ (276 reviews)
£6.99

WHY CUSTOMERS LOVE IT:
• No drilling required
• Strong adhesive backing
• Clean cable management

"Saved me hours on an installation." - James H.

[ADD TO CART →]

---

#5 SAFETY GLASSES (6 Pack)
[PRODUCT IMAGE]
⭐⭐⭐⭐⭐ (203 reviews)
£12.99

WHY CUSTOMERS LOVE IT:
• EN166 certified
• Anti-fog and anti-scratch
• Pack of 6 for teams

"Great quality at this price point." - Paul D.

[ADD TO CART →]

---

REMEMBER YOUR 10% OFF

Code WELCOME10 still works on any of these!

[SHOP ALL BEST SELLERS →]

Cheers,
Sarah

---

[Footer]
```

**Design Notes:**
- Product cards with images, reviews, prices
- Clear "why it's popular" reasons
- Individual add-to-cart buttons
- Final reminder of welcome discount

---

#### Email 5: Last Chance (Day 13)

**Timing:** 13 days after signup (1 day before discount expires)

**Subject Line Options:**
- "⏰ Your 10% off expires tomorrow"
- "[First Name], don't forget your discount"
- "Last chance: WELCOME10 expires at midnight"

**Preview Text:** "Your welcome discount vanishes in 24 hours"

**Email Template:**

```html
Subject: ⏰ Your 10% off expires tomorrow
Preview: Your welcome discount vanishes in 24 hours

---

Hi [First Name],

Quick heads up - your 10% welcome discount expires TOMORROW.

┌─────────────────────────────────────┐
│     YOUR CODE: WELCOME10            │
│     Expires: [DATE] at midnight     │
│                                     │
│     [USE MY DISCOUNT →]             │
└─────────────────────────────────────┘

After that, it's gone for good.

NOT SURE WHAT TO ORDER?

Here are some ideas based on what first-time customers typically grab:

🔌 For Electricians: Cable ties, cable clips, consumer unit accessories
🔧 For DIY: Screw assortment boxes, drill bits, wall plugs
🏗️ For Builders: Fixings, safety equipment, hand tools

Whatever you need, your 10% applies to everything on site.

ONE CLICK AWAY

[BROWSE & SAVE 10% →]

After midnight tomorrow, the code deactivates automatically.

Cheers,
Sarah

P.S. Got questions about what to order? Hit reply or call us on 0800 123 4567.

---

[Footer]
```

**Design Notes:**
- Clear urgency and deadline
- Simple, focused message
- Large CTA button
- Helpful suggestions for indecisive subscribers

---

### Sequence 2: Abandoned Cart (4 Emails)

**What:** Recover abandoned shopping carts and convert browsers to buyers.

**Trigger:** Cart created with items but no purchase within 1 hour

**Note:** Include cart contents dynamically in each email

#### Email 1: Gentle Reminder (1 Hour)

**Timing:** 1 hour after cart abandonment

**Subject Line Options:**
- "Did you forget something?"
- "You left something behind, [First Name]"
- "Your cart is waiting..."

**Preview Text:** "Your items are saved but won't last forever"

**Email Template:**

```html
Subject: You left something behind, [First Name]
Preview: Your items are saved but won't last forever

---

Hi [First Name],

Looks like you left some items in your cart. No worries - we've saved them for you!

YOUR CART:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

[DYNAMIC CART CONTENTS]
• [Product Name] x [Qty] - £[Price]
  [Product Image]
  
• [Product Name] x [Qty] - £[Price]
  [Product Image]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Subtotal: £[Amount]
Shipping: [Free/Amount]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

[COMPLETE MY ORDER →]

HAD A QUESTION?

Sometimes people leave carts because something wasn't clear:

❓ Delivery times? Most orders ship next day and arrive in 1-2 days.
❓ Returns? 30-day hassle-free returns on everything.
❓ Sizing help? Hit reply and we'll help you choose.

We're here if you need us.

Cheers,
GTSE Team

---

[Footer]
```

**Design Notes:**
- Show actual cart contents with images
- One clear CTA to complete purchase
- Address common concerns
- Helpful, not pushy tone

---

#### Email 2: Trust Builder (24 Hours)

**Timing:** 24 hours after abandonment

**Subject Line Options:**
- "Still thinking about it? Here's why customers love us"
- "Your cart + 3,000 five-star reasons to complete it"
- "What other customers say about [Product Name]"

**Preview Text:** "See what verified buyers say before you decide"

**Email Template:**

```html
Subject: Still thinking about it? Here's why customers love us
Preview: See what verified buyers say before you decide

---

Hi [First Name],

Still deciding on your order? Totally get it. 

Here's what other customers said about the items in your cart:

YOUR CART ITEMS:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

[Product Name] - £[Price]
[Product Image]

⭐⭐⭐⭐⭐ "Excellent quality, exactly as described. Will order again."
⭐⭐⭐⭐⭐ "Best value for money. Highly recommend."
⭐⭐⭐⭐⭐ "Fast delivery and great product."

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

WHY 15,000+ CUSTOMERS TRUST US:

✓ 4.8/5 star average from verified reviews
✓ 30-day money back guarantee
✓ Free returns - no quibble
✓ UK-based customer support
✓ Family business since 2012

YOUR CART TOTAL: £[Amount]

[COMPLETE MY ORDER →]

Not quite right? Reply and tell us what's holding you back.

Cheers,
Sarah

---

[Footer]
```

**Design Notes:**
- Product-specific reviews if available
- Trust signals prominently displayed
- Open invitation to reply with concerns
- Still helpful, slightly more persuasive

---

#### Email 3: Incentive (48 Hours)

**Timing:** 48 hours after abandonment

**Subject Line Options:**
- "Come back for 10% off your cart"
- "We added something to your cart: 10% off 🎁"
- "[First Name], is £[X.XX] holding you back?"

**Preview Text:** "Exclusive discount just for you - 48 hours only"

**Email Template:**

```html
Subject: Come back for 10% off your cart
Preview: Exclusive discount just for you - 48 hours only

---

Hi [First Name],

Your cart is still waiting - and now it's 10% cheaper.

We really want you to try GTSE, so here's an exclusive discount:

┌─────────────────────────────────────┐
│     10% OFF YOUR CART               │
│                                     │
│     Code: COMEBACK10                │
│     Expires: 48 hours               │
│                                     │
└─────────────────────────────────────┘

YOUR UPDATED TOTAL:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

[CART CONTENTS]
• [Product Name] x [Qty] - £[Price]
• [Product Name] x [Qty] - £[Price]

Subtotal: £[Amount]
10% Discount: -£[Savings]
NEW TOTAL: £[Reduced Amount]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

[CLAIM MY DISCOUNT →]

This code is unique to you and expires in 48 hours.

Questions? We're here:
📧 support@gtse.co.uk
📞 0800 123 4567

Cheers,
Sarah

---

[Footer]
```

**Design Notes:**
- Clear discount offer in box
- Show exact savings amount
- Urgency with 48-hour expiry
- Contact options for hesitant buyers

---

#### Email 4: Final Attempt (72 Hours)

**Timing:** 72 hours after abandonment

**Subject Line Options:**
- "Last chance for 10% off (cart clearing soon)"
- "We're about to clear your cart..."
- "Final reminder: your discount expires tonight"

**Preview Text:** "Your saved items and discount disappear at midnight"

**Email Template:**

```html
Subject: Last chance for 10% off (cart clearing soon)
Preview: Your saved items and discount disappear at midnight

---

Hi [First Name],

Final heads up - your cart and discount are expiring.

⏰ TONIGHT AT MIDNIGHT:
• Your cart items will be released back to stock
• Your 10% discount code deactivates

If you still want these items at the discounted price, now's the time:

YOUR CART:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

[CART CONTENTS with images]

Your Total: £[Amount] 
With COMEBACK10: £[Reduced Amount] ✓

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

[COMPLETE ORDER - SAVE 10% →]

IF IT'S NOT RIGHT FOR YOU...

No hard feelings. We'd genuinely like to know what put you off so we can improve. Hit reply with one line and we'll read every response.

Hope to see you soon,
Sarah

P.S. Already ordered elsewhere? You can unsubscribe below - we promise not to send cart reminders for something you've already bought.

---

[Footer]
```

**Design Notes:**
- Clear deadline creates urgency
- Graceful exit option
- Request feedback for non-converters
- Respectful of their decision

---

### Sequence 3: Post-Purchase Series (5 Emails)

**What:** Build relationship after first purchase, encourage reviews, and drive repeat purchases.

**Trigger:** First-time customer completes purchase

#### Email 1: Order Confirmation Enhancement (Immediate)

**Timing:** Immediately after purchase (supplements transactional confirmation)

**Subject Line Options:**
- "Thanks, [First Name]! You made a great choice"
- "Order confirmed - here's what happens next"
- "Welcome to the GTSE family! 🎉"

**Preview Text:** "Your order is on its way + what to expect"

**Email Template:**

```html
Subject: Thanks, [First Name]! You made a great choice
Preview: Your order is on its way + what to expect

---

Hi [First Name],

Thank you for your order! 🎉

You've just joined 15,000+ customers who trust GTSE for quality products at fair prices.

YOUR ORDER SUMMARY:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Order #: [ORDER_NUMBER]
Order Date: [DATE]

[ORDER CONTENTS]
• [Product] x [Qty] - £[Price]
• [Product] x [Qty] - £[Price]

Subtotal: £[Amount]
Shipping: [Amount/Free]
Total: £[Total]

Delivery Address:
[SHIPPING_ADDRESS]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

WHAT HAPPENS NEXT:

📦 Today: Your order is being picked and packed
🚚 Tomorrow: Order ships - you'll get tracking
📬 [Day 2-3]: Delivery to your door

[TRACK MY ORDER →]

GOT QUESTIONS?

📧 support@gtse.co.uk
📞 0800 123 4567 (Mon-Fri 9-5)

Reply to this email and a real human will get back to you.

Thanks again for choosing GTSE!

Sarah
Customer Success Manager

---

[Footer]
```

---

#### Email 2: Shipping Confirmation (When Shipped)

**Timing:** Triggered by shipping confirmation

**Subject Line Options:**
- "Your order is on its way! 🚚"
- "[First Name], your GTSE order just shipped"
- "Tracking info for order #[ORDER_NUMBER]"

**Preview Text:** "Track your delivery + what to expect when it arrives"

**Email Template:**

```html
Subject: Your order is on its way! 🚚
Preview: Track your delivery + what to expect when it arrives

---

Hi [First Name],

Great news - your order just left our warehouse!

SHIPMENT DETAILS:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Order #: [ORDER_NUMBER]
Carrier: [Royal Mail / DPD / etc]
Tracking #: [TRACKING_NUMBER]

Expected Delivery: [DATE]

[TRACK PACKAGE →]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

WHAT'S IN YOUR PACKAGE:

[ORDER CONTENTS with images]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

WHEN YOUR PACKAGE ARRIVES:

1. Check contents against packing slip
2. Test products before starting your project
3. Keep packaging for 30 days (just in case)

Something not right? Let us know within 30 days and we'll sort it.

Cheers,
GTSE Team

---

[Footer]
```

---

#### Email 3: Delivery Follow-Up (3 Days Post-Delivery)

**Timing:** 3 days after confirmed delivery

**Subject Line Options:**
- "How's everything, [First Name]?"
- "Quick check: did your order arrive okay?"
- "Is everything working as expected?"

**Preview Text:** "We want to make sure you're happy with your purchase"

**Email Template:**

```html
Subject: How's everything, [First Name]?
Preview: We want to make sure you're happy with your purchase

---

Hi [First Name],

Your order should have arrived by now. I wanted to check in and make sure everything's okay.

YOUR ORDER:
[Product Name(s) - thumbnail images]

A FEW QUICK QUESTIONS:

✓ Did everything arrive safely?
✓ Was it what you expected?
✓ Have you had a chance to use it yet?

[EVERYTHING'S GREAT 👍] [I HAVE A QUESTION 🤔] [SOMETHING'S WRONG 😕]

If anything isn't right, reply to this email or call us on 0800 123 4567. We'll make it right - no questions asked.

HELPFUL RESOURCES:

📖 How to get the best from your [Product Category]
🎥 Video guides on our YouTube channel
❓ FAQs on our website

[VIEW RESOURCES →]

Thanks for being a GTSE customer!

Sarah
Customer Success Manager

---

[Footer]
```

**Design Notes:**
- Quick satisfaction check
- Easy response buttons (if ESP supports)
- Proactive problem solving
- Helpful resources link

---

#### Email 4: Review Request (7 Days Post-Delivery)

**Timing:** 7 days after delivery

**Subject Line Options:**
- "Got 30 seconds? Tell us what you think"
- "[First Name], your opinion matters to us"
- "How did we do? Leave a quick review"

**Preview Text:** "Your review helps other customers make good decisions"

**Email Template:**

```html
Subject: Got 30 seconds? Tell us what you think
Preview: Your review helps other customers make good decisions

---

Hi [First Name],

You've had your [Product Name] for about a week now. 

Would you take 30 seconds to share your experience? Your review helps other customers make confident decisions.

YOUR RECENT PURCHASE:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

[Product Image]
[Product Name]
Purchased: [Date]

[LEAVE A REVIEW →]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

WHAT TO WRITE (If you're stuck):

• Did it meet your expectations?
• How was the quality?
• Would you recommend it to others?
• Any tips for other buyers?

Just a sentence or two really helps. We read every review and use feedback to improve.

AS A THANK YOU...

Leave a review on [any product] this month and you'll be entered to win a £50 GTSE voucher. We pick a winner on the 1st of each month.

Thanks for your support!

Sarah

---

[Footer]
```

**Design Notes:**
- Specific product and image
- Simple review prompts
- Incentive for motivation
- Respectful of their time

---

#### Email 5: Replenishment / Cross-Sell (21 Days Post-Purchase)

**Timing:** 21 days after purchase

**Subject Line Options:**
- "Running low? Here's 10% off your reorder"
- "Customers who bought [Product] also loved..."
- "[First Name], time to restock?"

**Preview Text:** "Complementary products + a thank-you discount"

**Email Template:**

```html
Subject: Customers who bought [Product] also loved...
Preview: Complementary products + a thank-you discount

---

Hi [First Name],

It's been a few weeks since you ordered your [Product Name]. How's it working out?

CUSTOMERS WHO BOUGHT THIS ALSO GRABBED:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

[Product 1 Image]
[Product 1 Name]
£[Price] ⭐⭐⭐⭐⭐ ([X] reviews)
[ADD TO CART →]

[Product 2 Image]
[Product 2 Name]
£[Price] ⭐⭐⭐⭐⭐ ([X] reviews)
[ADD TO CART →]

[Product 3 Image]
[Product 3 Name]  
£[Price] ⭐⭐⭐⭐⭐ ([X] reviews)
[ADD TO CART →]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

THANK YOU DISCOUNT

As a returning customer, here's 10% off your next order:

Code: THANKS10
Expires: [Date - 14 days]

[SHOP NOW →]

Need to reorder [Original Product]? Use the same code.

Cheers,
Sarah

---

[Footer]
```

**Design Notes:**
- Personalized product recommendations
- Cross-sell based on purchase history
- Loyalty discount encourages return
- Easy reorder option

---

### Sequence 4: Re-Engagement Series (4 Emails)

**What:** Wake up subscribers who haven't engaged (opened/clicked) in 90+ days.

**Trigger:** No email opens or clicks in 90 days, but was previously active

#### Email 1: We Miss You (Day 1)

**Subject Line Options:**
- "We miss you, [First Name] 💔"
- "It's been a while..."
- "[First Name], are you still there?"

**Preview Text:** "Haven't seen you in a while - is everything okay?"

**Email Template:**

```html
Subject: We miss you, [First Name] 💔
Preview: Haven't seen you in a while - is everything okay?

---

Hi [First Name],

We noticed you haven't opened our emails in a while. 

Is everything okay?

Maybe:
• Our emails are going to spam? (Add us to contacts!)
• You're getting too many emails? (Update preferences below)
• You're just busy? (We get it!)

WE'VE BEEN BUSY TOO:

Here's what you might have missed:
• 200+ new products added
• Extended range of [Product Category]
• Even faster delivery options
• [Recent improvement or news]

COME SEE WHAT'S NEW:

[BROWSE NEW ARRIVALS →]

If you'd rather not hear from us, no problem - update your preferences or unsubscribe below. We'd hate to clog up your inbox.

But we'd love to have you back.

Cheers,
Sarah

---

[Footer with prominent unsubscribe]
```

---

#### Email 2: What's Changed (Day 5)

**Subject Line Options:**
- "A lot has changed - come take a look"
- "Here's what's new at GTSE"
- "Big changes since you've been away"

**Preview Text:** "New products, better prices, faster delivery"

**Email Template:**

```html
Subject: Here's what's new at GTSE
Preview: New products, better prices, faster delivery

---

Hi [First Name],

Things have been happening at GTSE. Thought you might want to know!

WHAT'S NEW:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

🆕 NEW PRODUCTS
[Image of new product range]
We've added [X] new products including [category highlights].

[EXPLORE NEW RANGE →]

💷 BETTER VALUE
Price reductions on [X] popular items. Same quality, better prices.

[SEE PRICE DROPS →]

🚚 FASTER DELIVERY
Now offering same-day dispatch on orders before 2pm.

📦 FREE DELIVERY
Threshold reduced to £35+ orders.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

WELCOME BACK OFFER:

Here's 15% off to celebrate your return:

Code: MISSEDYOU15
Valid for 7 days

[CLAIM MY DISCOUNT →]

Hope to see you soon!

Sarah

---

[Footer]
```

---

#### Email 3: Incentive (Day 10)

**Subject Line Options:**
- "20% off to welcome you back"
- "Your best offer yet: 20% off everything"
- "Last attempt: here's 20% off"

**Preview Text:** "Our biggest discount - but only for 5 days"

**Email Template:**

```html
Subject: 20% off to welcome you back
Preview: Our biggest discount - but only for 5 days

---

Hi [First Name],

Okay, we're pulling out all the stops.

We really want you back, so here's our BEST offer:

┌─────────────────────────────────────┐
│     20% OFF EVERYTHING              │
│                                     │
│     Code: COMEBACK20                │
│     Expires: 5 days                 │
│                                     │
│     [SHOP NOW →]                    │
└─────────────────────────────────────┘

This is the biggest discount we offer - normally reserved for our best customers on special occasions.

It works on everything:
• Cable ties and fixings
• Hand tools and power tools
• Safety equipment
• Storage and organization
• Everything on our site

No minimum order. Free delivery on £35+.

[CLAIM 20% OFF →]

After 5 days, this code expires and I won't be able to extend it.

Cheers,
Sarah

---

[Footer]
```

---

#### Email 4: Final Goodbye (Day 15)

**Subject Line Options:**
- "Is this goodbye? 👋"
- "Should we stop emailing you?"
- "One last thing before we go..."

**Preview Text:** "Click to stay or we'll remove you from our list"

**Email Template:**

```html
Subject: Should we stop emailing you?
Preview: Click to stay or we'll remove you from our list

---

Hi [First Name],

I've sent a few emails over the past couple of weeks and haven't heard back.

No hard feelings - maybe GTSE just isn't for you right now. That's okay.

But I don't want to fill up your inbox if you're not interested.

So here's the deal:

[KEEP ME SUBSCRIBED →]
Click if you want to stay on our list

[UNSUBSCRIBE ME →]
Click if you want us to stop

If I don't hear from you in 7 days, I'll remove you from our list automatically. You can always come back later by signing up again.

Thanks for your time either way. If you ever need cable ties, fixings, or tools - you know where to find us.

All the best,
Sarah

P.S. If you clicked nothing by accident - here's one final chance at 20% off: COMEBACK20

---

[Footer]
```

**Design Notes:**
- Clear choice: stay or go
- Automatic removal protects list health
- Respectful, graceful exit
- Final incentive for fence-sitters

---

### Sequence 5: Win-Back Series (3 Emails)

**What:** Re-engage customers who haven't purchased in 6+ months but were previously active buyers.

**Trigger:** No purchase in 180+ days, has previous purchase history

#### Email 1: We Miss Your Business (Day 1)

**Subject Line Options:**
- "It's been 6 months, [First Name]. Come back?"
- "We haven't seen you in a while..."
- "Your GTSE account misses you"

**Preview Text:** "Here's 15% off to welcome you back"

**Email Template:**

```html
Subject: It's been 6 months, [First Name]. Come back?
Preview: Here's 15% off to welcome you back

---

Hi [First Name],

We noticed it's been a while since your last order. 

Everything okay?

We wanted to reach out because:
• We genuinely miss your business
• We want to make sure nothing went wrong
• Things have changed since you were last here

YOUR LAST ORDER:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Order Date: [LAST_ORDER_DATE]
Products: [LAST_ORDER_PRODUCTS]
Order Value: £[AMOUNT]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

WHAT'S NEW SINCE THEN:

📦 [X] new products added to our range
💷 Free delivery threshold reduced to £35
🚚 Same-day dispatch on orders before 2pm
⭐ 1,000+ new 5-star reviews

WELCOME BACK OFFER:

As a valued past customer, here's 15% off your return:

Code: WELCOMEBACK15
Valid: 14 days

[SHOP NOW - SAVE 15% →]

Questions? Hit reply - I'd love to hear from you.

Sarah
Customer Success Manager

---

[Footer]
```

---

#### Email 2: New Products Since Your Last Visit (Day 7)

**Subject Line Options:**
- "See what's new since you last shopped"
- "New arrivals you might have missed"
- "Fresh stock just landed (your 15% still works)"

**Preview Text:** "New products in [Category] + your discount reminder"

**Email Template:**

```html
Subject: See what's new since you last shopped
Preview: New products in [Category] + your discount reminder

---

Hi [First Name],

Since your last order ([X] months ago), we've added lots of new products you might like.

BASED ON YOUR PREVIOUS PURCHASES:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

[Recommended Product 1 - based on purchase history]
[Image] [Name] £[Price]
"Perfect if you liked [Previous Product]"
[VIEW PRODUCT →]

[Recommended Product 2]
[Image] [Name] £[Price]
"New addition to our [Category] range"
[VIEW PRODUCT →]

[Recommended Product 3]
[Image] [Name] £[Price]
"Customer favorite with [X] 5-star reviews"
[VIEW PRODUCT →]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

NEED TO RESTOCK?

Your previous order included:
• [Product Name] - [REORDER →]
• [Product Name] - [REORDER →]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

REMINDER: Your 15% discount is still active

Code: WELCOMEBACK15
[APPLY DISCOUNT & SHOP →]

Cheers,
Sarah

---

[Footer]
```

---

#### Email 3: Final Offer + Feedback (Day 14)

**Subject Line Options:**
- "Before you go: one last offer"
- "20% off + we'd love your feedback"
- "Final attempt: here's our best deal"

**Preview Text:** "Our biggest discount + tell us why you left"

**Email Template:**

```html
Subject: 20% off + we'd love your feedback
Preview: Our biggest discount + tell us why you left

---

Hi [First Name],

This is my last email in this series.

Before I stop, I wanted to offer two things:

1. OUR BEST DISCOUNT:

┌─────────────────────────────────────┐
│     20% OFF YOUR NEXT ORDER         │
│                                     │
│     Code: FINALCHANCE20             │
│     Expires: 7 days                 │
│                                     │
│     [SHOP & SAVE 20% →]             │
└─────────────────────────────────────┘

2. YOUR HONEST FEEDBACK:

If you're not coming back, I'd genuinely like to know why. It helps us improve. Could you take 30 seconds to tell me?

What happened?
[ ] Found a better supplier
[ ] Product quality issues
[ ] Price too high
[ ] Delivery problems
[ ] Don't need products anymore
[ ] Other: ____________

[SUBMIT FEEDBACK →]

Your feedback goes directly to our team - we read and discuss every response.

Whatever you decide, thanks for being a GTSE customer. Our door is always open if you need us in the future.

Best regards,
Sarah
Customer Success Manager

---

[Footer]
```

**Design Notes:**
- Final escalated offer (20%)
- Exit survey for churn learnings
- Graceful close to relationship
- Door left open for future return

---

## Examples

### Example 1: DTC Ecommerce Implementation

**Business:** GTSE (Trade supplies, DTC + B2B)
**Platform:** Klaviyo
**Goal:** Increase email revenue from 15% to 25% of total

**Implementation:**

1. **Welcome Series (5 emails)**
   - Implemented with 10% discount code
   - Average open rate: 62%
   - Average conversion rate: 8.2%
   - Revenue per recipient: £4.85

2. **Abandoned Cart (4 emails)**
   - Email 1 (1hr): 45% open rate, 8% conversion
   - Email 2 (24hr): 38% open rate, 5% conversion
   - Email 3 (48hr with 10% off): 41% open rate, 12% conversion
   - Email 4 (72hr final): 32% open rate, 3% conversion
   - Overall cart recovery rate: 18%

3. **Post-Purchase (5 emails)**
   - Review request response rate: 12%
   - Cross-sell email revenue: £2,340/month
   - Repeat purchase rate increase: +23%

4. **Re-engagement (4 emails)**
   - Reactivated 340 dormant subscribers
   - List cleaned of 1,200 inactive addresses
   - Improved deliverability by 6%

5. **Win-back (3 emails)**
   - Recovered £8,400 in first quarter
   - Average order value from win-back: £68 (+15% vs normal)
   - 22% win-back success rate

**Results after 6 months:**
- Email revenue: 27% of total (+12%)
- List health score: 94 (up from 76)
- Customer lifetime value: +18%

---

### Example 2: B2B Trade Account Implementation

**Business:** GTSE Trade Accounts
**Platform:** ActiveCampaign
**Goal:** Nurture new trade account holders

**Modified Sequences:**

**Trade Welcome Series (adjusted):**
- Email 1: Welcome + introduce dedicated account manager
- Email 2: How to use trade portal + bulk ordering
- Email 3: Credit terms and payment options
- Email 4: Volume discount structure
- Email 5: Invite to QBR scheduling

**Trade Post-Purchase:**
- Focus on reorder reminders based on usage
- Cross-sell related trade products
- Quarterly spend summaries

**Trade Win-Back:**
- Triggered at 30 days (not 180) for trade accounts
- Offer dedicated account review
- Include credit terms improvement offer

---

## Output Format

### Email Sequence Documentation

```markdown
# [Sequence Name] Email Series

## Overview
- **Trigger:** [What starts this sequence]
- **Emails:** [Number of emails]
- **Duration:** [How long the sequence runs]
- **Goal:** [What we're trying to achieve]

## Email Schedule
| Email | Timing | Subject | Purpose |
|-------|--------|---------|---------|
| 1 | Immediate | [Subject] | [Goal] |
| 2 | Day 2 | [Subject] | [Goal] |
| ... | | | |

## Performance Benchmarks
| Metric | Target | Industry Avg |
|--------|--------|--------------|
| Open Rate | XX% | XX% |
| Click Rate | XX% | XX% |
| Conversion | XX% | XX% |

## Exit Conditions
- [When subscribers exit sequence]
- [Suppression rules]
```

---

## Related Skills

- [Content Strategy](../content-strategy/SKILL) - Email content planning
- [Social Content](../social-content/SKILL) - Cross-channel coordination
- [B2B Account Penetration](../../b2b/account-penetration/SKILL) - Trade account emails
- [Pricing Strategy](../../ecommerce/pricing-strategy/SKILL) - Promotional email offers

---

## Appendix

### A: Subject Line Best Practices

| Element | Best Practice | Example |
|---------|--------------|---------|
| Length | 30-50 characters | "Your order is on its way 🚚" |
| Personalization | Use first name sparingly | "[First Name], your 10% off expires" |
| Urgency | Be specific, not fake | "Expires midnight tonight" not "HURRY!!!" |
| Emojis | Max 1-2, match brand | ✅ 🎁 📦 not 🔥🔥🔥💥💥 |
| Questions | Drive curiosity | "Did you forget something?" |
| Numbers | Add specificity | "5 products our customers love" |

### B: Optimal Send Times (UK)

| Day | B2C Best Times | B2B Best Times |
|-----|----------------|----------------|
| Monday | 8am, 1pm | 10am, 2pm |
| Tuesday | 8am, 8pm | 10am, 2pm |
| Wednesday | 8am, 1pm | 10am, 2pm |
| Thursday | 8am, 8pm | 10am, 2pm |
| Friday | 8am | 10am |
| Saturday | 10am | Avoid |
| Sunday | 8pm | Avoid |

### C: Email Platform Comparison

| Feature | Klaviyo | Mailchimp | ActiveCampaign |
|---------|---------|-----------|----------------|
| Ecommerce focus | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐ |
| Automation | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐⭐ |
| Segmentation | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐ |
| Reporting | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ |
| B2B features | ⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐⭐ |
| Price | $$$ | $$ | $$ |

### D: Compliance Checklist

- [ ] Unsubscribe link in every email
- [ ] Physical address included in footer
- [ ] Clear sender identification
- [ ] Consent properly collected (GDPR)
- [ ] Easy preference management
- [ ] Processing basis documented
- [ ] Soft opt-in for customers (PECR compliant)
- [ ] Double opt-in for newsletter signups

---

*Version 1.0.0 | Last Updated: 2025*
*For GTSE internal use - Confidential*
