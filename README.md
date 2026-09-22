# Hollowmere

A brand site for Hollowmere, a fictional cider house. It has no images: the
orchard in the hero, the four seasons, and the bottles are all drawn in code.

Live: https://bxzex.github.io/orchard/

## The orchard

The hero is a canvas scene rebuilt every frame:

- **Trees** grow by recursive branching from a seed. There are 48 of them,
  each grown once from its own seed, so every season redraws the same trees.
  The canopy is eleven lobes drawn in three passes: a shadowed underside, a
  body and a lit crown. Fruit and blossom sit inside the lobes.
- **Rows** recede to a vanishing point. Each tree's position and size come
  from one projection factor, and the scene draws far to near.
- **Wind** rotates each branch around its parent's tip by an amount that grows
  with the square of its depth. Trunks stay still and twigs move most.
- **Seasons** swap the sky, sun height, hills, ground, canopy, fruit and snow.
  Switching crossfades from a snapshot of the last frame over 650 ms.
- **Scroll parallax** moves the sun, hills and ground at different rates.
- Film grain is drawn once to a tile and used as a pattern. Rebuilding it
  per frame was the single biggest cost, and moving it roughly doubled the
  frame rate. Branch parents are resolved when the tree grows, not looked up
  by string key every frame.

The year section renders the same scene four times, one card per season.
Clicking a card sets the hero to that season.

## The rest of the site

- Four ciders with SVG bottles, labels and fruit drawn per product, a dry to
  sweet dial and a small basket
- A booking form: the next fourteen days with Monday and Tuesday closed,
  weekday and weekend time slots with stable pretend availability, a guest
  stepper that updates the price, inline validation that scrolls to the first
  problem, and a confirmation with a reference code. Nothing is sent. The page
  says so twice.
- Counters and fade-ins on first view, all switched off under
  `prefers-reduced-motion`, which also freezes the wind
- A mobile menu, and a layout that holds at 390px with no horizontal scroll

## Notes

One HTML file. No images, no libraries, no build step. Hollowmere and its
ciders are invented.

Built by [bxzex](https://bxzex.com).
