# KongsiBill

A small web app that splits a restaurant bill fairly between friends, including Malaysian service charge and SST.

*Kongsi* means "to share" in Malay.

## The problem

When friends eat out, not everyone orders the same things. Dividing the total evenly is unfair, and working out each person's share by hand, with service charge and tax on top, is slow and easy to get wrong. KongsiBill does the maths and gives everyone a number they can pay.

## Features

- Add the people at the table and the items you ordered
- Choose who shares each item. Its price is split evenly between them
- Optional 10% service charge and 6% SST, with SST applied after the service charge
- Optional rounding of each person's total to the nearest 5 sen
- Per-person breakdown: food, service charge and SST
- One-tap copy of the summary to paste into WhatsApp
- Your table is saved in the browser, so a refresh does not lose it
- Works on phones and desktop, with keyboard support

## How to use

1. Add everyone at the table.
2. Add each item with its price. By default everyone shares it.
3. Tap names under an item to change who shares it.
4. Pick which charges to apply.
5. Read the receipt on the right, then tap **Copy for WhatsApp**.

Use **Try an example** to fill in a sample table.

## How the split works

For each person:

```
food    = sum of (item price / number of people sharing it)
service = food x 10%                (if enabled)
sst     = (food + service) x 6%     (if enabled)
total   = food + service + sst      (rounded to nearest 5 sen if enabled)
```

Example: someone who ordered a single RM 10.00 dish pays
RM 10.00 + RM 1.00 service + RM 0.66 SST = RM 11.66, which rounds to **RM 11.65**.

Items that nobody is sharing are not counted, and the app warns you about them.

## Run it

No install or build step. Open `kongsibill.html` in any modern browser.

## Built with

- HTML, CSS and vanilla JavaScript, with no libraries or frameworks
- `localStorage` to keep the table between visits
- Google Fonts (Bricolage Grotesque and IBM Plex Mono), with system font fallbacks

## Ideas for next steps

- Track who paid and who still owes them
- Support other tax and service charge rates
- Share a link that opens the same table on a friend's phone
- Dark mode

## Author

Made by [JeffWorks](https://jeefryhafizuddin.github.io/portfolio/#contact), Jeefry Hafizuddin Bin Abdullah, Computer Science student at UNITEN.
