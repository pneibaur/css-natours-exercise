# CSS concepts Notes

---

## Three pillars of HTML and CSS

1. reponsive design - one website that responds across all devices
fluid layouts
Media Queries
Responsive Images
Correct Units
Desktop first or Mobile first

2. Maintainable and Scalable Code
clean
easy to understand
growth
reusable
how to organize files
how to name classes
how to structure HTML

3. Web Performance
less HTTP requests
less code
compress code
use a CSS precompressor like Sass
less images
compress images

---

## What happens behind the scenes

Load HTML ---> Parse HTML and load CSS ---> resolve conflicting CSS Declarations known as cascade ---> all is stored in CSS Object Model (much like the DOM) ---> website rendering: the visual formatting model

### resolve conflicts

there are several sources for CSS. the author (you) writing the stylesheet. The user changing their default browser font settings for example. and finally, the browser also has default settings (like a blue underlined link)

it resolves these by importance > Specificity > Source Order

**order of importance**
1. User !important
2. Author !important
3. Author
4. User declarations
5. default browser

if the rules are of the same importance (like when the author has two declarations in the same sheet)
follow highest to lowest specificity

**Order of Specificity**
1. Inline Styles
2. IDs
3. Classes, pseudo-classes, attribute
4. Elements and pseudo elements

these are ranked and counted in a (#,#,#,#) style. it counts how many occurences there are of each rank, and chooses from there. if there are any inline styles, those outrank everything else.... and any element with multiple inline styles will outrank the other inline styles with only one... the next applies to IDs, and so on. one style declaration block may pan out (0,1,2,1), and the next one that selects the same element may pan out as (0,2,3,1) - and the latter will win because there's a '2' in the 2nd position that outranks the '1' in the 2nd position in the first choice. 

finally, if all other things are equal, the last declared style will be applied. 

### TIPS
- only use !important as a last resort. it helps with more maintainable code. 
- inline styles will always have priority over external stylesheets
- a selector with 1 # will always have more priority over classes
- same with 1 class over elements
- the universal selector * has no specificity
- rely more on specificity than order of selectors. 
- rely on order when using a 3rd party stylesheet. always put yours last. 