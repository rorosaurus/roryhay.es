---
layout: post
title: Some stores are selling broken ESP32-C3 Super Mini's
date: 2024-06-29 13:32:20 +0300
description: 2.5-4x worse RF makes them totally useless # Add post description (optional)
img: blog/esp32-c3-super-mini/esp32-c3-super-mini-flaw.jpg # Add image post (optional)
fig-caption: Careful when purchasing!  # Add figcaption (optional)
github-repo: # Add github repo (optional)
tags: [Maker, Soldering, LEDs, ESP32, WLED]
---

Can you spot the difference between these two development boards?

With my latest shipment of C3 Super Mini's, I'm unable to connect to Wi-Fi about 95% of the time. When I can connect, I'm seeing 10-16 dBm less signal strength compared to previous shipments. That translates to a 2.5-4x worse overall Wi-Fi connection, which is effectively a death sentence for the already minimal, compact antenna design.

I found this out after buying in bulk! 😳 Fortunately it was an AliExpress Choice purchase, so I'm able to submit a free refund.

So what went wrong here? What can we learn about the importance of good RF design? And how can we avoid falling victim to sellers cost optimizing a product into oblivion?

# Investigating the fault

## Differences I found on the faulty boards
* Can't connect to Wi-Fi, but can host its own AP fairly reliably.
  * Perhaps transmit performance is ok, but receive is poor?
* Unmarked LDO for 3.3V
  * Tested with a 1000uF capacitor across 3.3V and GND and verified poor Wi-Fi was not due to this component
* PCB panelization via mouse bites instead of V-Cut
  * I can't imagine this affects anything, but it does hint to a wholly different PCB design - so [let's look closer!](/assets/img/blog/esp32-c3-super-mini/esp32-c3-super-mini-flaw.jpg)
* Some components are laid out slightly differently. Specifically the oscillator in the top right and some capacitors in the top left are significantly closer to the antenna...
* Despite being the same overall dimensions, this board has a **full 1mm less clearance for the antenna section!**

## [Espressif's design recommendations](https://docs.espressif.com/projects/esp-hardware-design-guidelines/en/latest/esp32/pcb-layout-design.html#rf)
> There should be no high-frequency signal traces routed close to the RF trace. The RF antenna should be placed away from high-frequency components, such as crystals..

Welp, that crystal oscillator is now awfully close I think! In fact, the section on typical layout problems [specifically defines our case](https://docs.espressif.com/projects/esp-hardware-design-guidelines/en/latest/esp32c3/pcb-layout-design.html#tx-performance-is-not-bad-but-the-rx-sensitivity-is-low):

>TX performance is not bad, but the RX sensitivity is low.
>
>Analysis: Good TX performance indicates proper RF impedance matching. Poor RX sensitivity may result from external coupling to the antenna. For instance, the crystal signal harmonics could couple to the antenna.
>
>Solution: Keep the antenna away from crystals. Do not route high-frequency signal traces close to the RF trace

Combine that with the 1mm reduced clearance for the antenna, and it's no wonder why the Wi-Fi performance is poor!

Some people from the WLED Discord have even seen this type of poor performance on S3 Zero models, where the clearance is reduced but the crystal is distant - leading me to think this spacing is the primary, but not the only, culprit.

# How to avoid buying bad boards
On AliExpress, I'd recommend **ordering a single board first** to confirm what you receive before a bulk order. In future orders, **stick with a seller you've had good results with** - don't be tempted by a new store that saves you a few pennies.

Of course, there's no guarantee that what you order next time is identical. **Make sure your order has the "AliExpress Choice Commitment"**, where AliExpress will step in to help you resolve refund/returns if needed.

If you find a listing that uses this broken design, please leave a review and message the seller directly! You can link them to this post if you'd like. I've contacted the seller of my broken boards and the customer service rep told me they'd pass this information on to the engineering team. 🤞 Hopefully we can reduce the chance of people buying these boards accidentally!

## You can't trust the listing photos
[Here's the listing where I got broken boards.](https://www.aliexpress.us/item/3256806148201179.html) Notice that the listing uses pictures from the original, working board design! What arrives isn't necessarily what is pictured!

## Purchase from vetted Sellers
Ask others in the community what sellers/listings they use. Here's what I have so far:
* [My original AliExpress purchase](https://www.aliexpress.us/item/3256805910402296.html)
* [TENSTAR ROBOT Store (recommended by WLED Discord users)](https://www.aliexpress.us/item/3256805781327184.html)