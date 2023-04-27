# Foundations of Web Development
01. In your own words, why do we use Git?
    > | To store our projects and track the changes we've made to our code as we build it. If we're working with others, it'll help to see who did what and timestamp the projects as they go. |

02. In the terminal, what is the command `mkdir` used for?
    > | mkdir = Make Directory = makes a new directory (folder) for storing projects and other goodies 📂 |

03. What is a ***pseudo-class*** and what are some of the most common ones you think you will use?
    > | pseudo-classes add styles to selectors. The most common ones I'll use will probably be :hover to add style to an element when the cursor hovers over it, like making it glow or bounce. :visited to add a different color or cause a link to fade if it's been visited or :link for the same effects if it hasn't been visited. I'm not too sure what other ones will be used a lot.  |

04. What is ***specificity*** and how might you use it to your benefit?
    > | Specificity gives priority based on its placement and the level of selector that's used. It'll be helpful because I can use pseudo classes or elements to make general changes as a whole, then use inline styling for more specific circumstances to overwrite the lower level elements and pseudo classes. |

05. What problems do you think you could run into if you over-utilized the `!important` feature?
    > | !important will override any previous styling rules for a specific property. It can only be overridden by using another !important rule. Overusing the !important rule could result in things getting muddled or everything accidentally looking like the final !important rule's properties so the previous ones would all need fixing. |

06. What are the three components that makeup a `CSS` rule? <br> Example:

    ```css
        h1 {
            color: rgba(255, 210, 33, .75);
        }
    ```

    > | selector: h1, property: color, and value: rgba|

07. How do you think good design influences people when visiting a website, and what sorts of things could you convey through design alone?
    > | On the surface, good design just shows more care and dedication. People will prefer to look at something visually appealing that doesn't seem boring or too busy. Keeps their eyes flowing through the page, isn't too harsh with the colors or the mixing of elements. The right style can convey a lot of emotion. Softer colors and rounder cards will help with a sense of ease. If you're wanting a site that conveys energy you'll want brighter colors or conflicting colors. The right design can convey an emotion you're wanting people to feel and it can make the site more memorable if it's done in an uncommon way,  |

08. What is the purpose of ***wireframing***?
    > | This one I didn't know, so I had to google it. But it seems like this is more like what we're doing right now. It's used to build the layout and design of a website, but the links and buttons aren't active. It's just to build it out and see how it all works together visually, before going deeper and adding that functionality.  |

09. Do you think wireframes are worth the time, energy, and effort that they require? Why or Why not?
    > | Reading more on these, I do think they'd be worth the time and energy. I love photography and art. In photography you have to go through aaaaaall the shots you took, then find 50 or so that you liked. From there you have to break it down to maybe 30. Then you do a contact sheet with 15 or so that you love from them all depending on what you're doing. It helps you figure out what shots you like best and what ones work best together. With art, you want to sketch out ideas, make pallettes of colors to see how they compliment, and see what works best together before you start the final image. It makes sense that you'd want to design things out first before the functionality, to make sure everything just looks good together. It wouldn't make sense to try designing and functioning at the same time. If you have to go back and adjust the design while you're working on the function, it could mess up the functioning and you'd have to fix two things then. Measure twice and cut once.  |

10. Define the display `:flex property:`
    > | this allows us to use different properties on a container to allow anything within that container to be more flexible in their design. |

11. What `CSS` properties affect the size of a box model?
    > | The margin to adjust how far out the bounds of the box push, the border to adjust the size of the actual border of the box, and the padding to adjust how far the inner contents of the box sit from the border.  |
