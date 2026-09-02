# images

Artwork photos go here.

1. Save the file in this folder, e.g. `piece-1.jpg`. Export around 2000px on the
   long edge — big enough to look sharp on a retina screen, small enough to load
   fast.
2. In `index.html`, find the matching `<div class="frame ...">` and replace the
   `<span class="frame-label">Image 1</span>` line with:

   ```html
   <img src="images/piece-1.jpg" alt="Short description of the piece" />
   ```

The placeholder box's border, tint and fixed proportions disappear on their own
once an `<img>` is inside the frame, so the photo keeps its own shape — there's
nothing else to adjust.
