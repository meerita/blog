---
title: A very common UX dilemma with the listings on e-commerce websites
date: '2019-09-16 19:05:31'
layout: post
category: Design
summary: E-commerce websites have the possibility of changing the number of items
  per page, but this functionality does not always fit customer the expectation and
  usually causing more harm than good. A small analysis about this topic and a possible
  solution to this problem of UX.
subtitle: How to solve View X items per page problems
---

I recently read a survey on Twitter about how to display paginated items that have just been changed using the quantity filter (ex. View 20, 30, 40 items per page, etc.) that, by choosing a higher or lower amount, it changes radically the initial UX of the list. When that happens you already lose your sense of direction and position. **This behavior is almost standard on the internet** and it is surprising that few websites fixed it logically. What follows is just my point of view and possible solution as a regular customer of e-commerce sites and therefore, I have not implemented it with real customers yet, nor do I know if the design solution is the best, but the idea is to develop the logical rules so that the design system makes sense and can be tested on the field.

Let's say our customer uses our e-commerce website and searches for something that returns many results. That list returns 25 items per page out of a total of 500 and the customer starts browsing it, completing 3 pages in total (see Fig. 1). Our customer starts viewing all items (light cyan on fig. 1) and starts moving to the following pages and stops at the page 3. Here is when the customer decides 25 items per page is not enough for browsing items, so it uses the display filter at the top of the list, and change the pagination to 100 items per page.  In the following graphic, you can see in light cyan, the items that the customer has seen already, and strong cyan are the current items the customer is seeing, gray items are those who weren't reviewed yet by our customer:

<img src="/images/25pp.svg" alt="" width="554" height="715" class="display--block" style="margin: 0 auto"  loading="lazy">

What will happen if our customer changes the items per page option? The usual thing is to experience a full reload of the entire list (fig. 2), and it returns our customer to page one, in that moment the user is again watching the first 3 or 4 items of the list that was already seen. Everything has to be seen again. What a pity. There are also other variants, which I encounter in the past and they are even way more painful: such as leaving you on the same page (fig. 3), with 100 items, but the previous pages also have 100 items, so the last item you had seen now is on previous pages leaving you with huge unreviewed items in in the middle. You land in the page 3 but you don't recognize any item. In either case you are lost and you have to browse everything again, but in the last example (the fig. 3 one), you clearly have to browse backwards to catch up where you have left the last browsed items.

<div class="display--grid md-grid-template-columns--2">
  <img src="/images/100pp.svg" alt="" class="display--block" style="width: 80%; margin: 0 auto" loading="lazy">
  <img src="/images/100pp-mad.svg" alt="" class="display--block" style="width: 80%; margin: 0 auto" loading="lazy">
</div>

This approach brings out one of the most endemic problems of the listings on web pages. This is a bad practice that goes unnoticed, frustrates our customer that has to waste time looking back and foward at all the items on the list, it also causes the customer to lose instantly the point where it was browsing. For example, if the customer is looking the Item 223 on page 5, now this item is on page 3, therefore, the customer has to go through page 2 or 3 and search for the item to continue checking where everything is. People do not have time to make maths to calculate on which page the last viewed item is and in what order that item currently is.

What should be the ideal behavior for these types of cases is the big question. And for that we have to analyze the initial intention of our customers: **see more or less items in the list, but in the current position**. If we review this premise closely, we can understand that the ideal case would be, at the point where [the customer] is, we must display x amount of items to complete the sample the desired sample. In other words: if you have been seeing 25 items per page, and now you say you want 100, you should add 75 more items to the current page you are viewing (fig. 4), the previous ones should remain at 25 and the following ones, at 100 unless the customer again change its mind.

<img src="/images/100pp-good.svg" alt="" class="display--block" style="max-width: 50%; margin: 0 auto" loading="lazy">

In this example (fig. 4) we can see the possible solution: you reload (or you don't) the page results but you just leave the customer on the same spot than before. The customer has lots of interesting and obvious options: it can go back and see exactly what was browsed or it can keep browsing the new additions and keep browsing 100 items per page. So, in an ideal world, the customer would never see a full reload, but an injection of more items to the page is browsing completing the 100, for this case. Even if the customer wants to remove it should do the same, trim the 100 back to 25 per page, the previous pages aren't changed at all.

This kind of interaction is good for many reasons: the customer doesn't experience any kind of "full reset". It will not be taken to the page 1 with 100 results, it will see the same page 3, but with 100 items. The customer has memorized two pages of items already while reviewing all, we don't change anything of that, therefore, is free to go back and find the same items has reviewed in pages with 25 items per page and move forward with 100 per page. The customer can change the filter any time, like loading 100 items and then return to 25 again, we should reload that page with the correct amount of items. If the customer re-filter again the list in any point, that page and any next page will display the correct amount of items.

To resume on how to create a good listings browsing experience:

1. Never full reset the progress made by a customer.
2. Always inject—or reset—the current page with the selected amount of items.
3. Always show the previous ones with the old options.
4. Always show next pages according to the new filter.
5. Any change to the filter will update only the following pages.

For sure these rules does not apply to the rest of the filters. We will have to do the full reset and there is no logical option here. If you're in the page 3, you cannot remain there if you change the price filter, you need to start from 0 because you will need to review backwards any new change. This logical set of rules is only applies to items per page filters.