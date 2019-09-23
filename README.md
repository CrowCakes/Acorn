Acorn is a portal website for Microgenesis built on the Wordpress framework and hosted on a CentOS VM server.
This document aims to explain what Acorn's files and codes do.



###### Files
Wordpress keeps the webpages in a MySQL database, but for redundancy's sake, 
the edited files are saved in Acorn's GitHub repository at https://github.com/CrowCakes/Acorn

styles.css is Wordpress's 2019 theme css, edited for some of the styles seen in the website.

Wordpress offers a more user-friendly approach to adding and editng css with their Customize page, which is where a majority of Acorn's css code can be found.
This code is saved under additional_css.css

Each page is labled XXXXX_page_body.html, where XXXXX refers to a certain department in Microgenesis.
Each contain a similar structure, which will be explained in the next section of this document.

acorn-.png and mgen_logo.png are images used in the header and the footer of Acorn, respectively.

The test folder contains irrelevant assets used during the prototyping and experimentation process of the creation of the site.
It can be removed to no impact on the website.



## HTML Body Structure
As Wordpress loads in the same header and footer for each webpage, the only concern for each individual webpage is the body content.
Each page body contains a single div, containing a table with only 1 row of 3 cells holding the contents of the page.

The first and last cell contain nested divs, the parent containing a name, and the child, containing a description of that name.
There may be 0-3 of these divs in those cells.
Additionally, a second table is commented out below this first table, in case more descriptions need to be added in the future.

The middle cell contains links to various websites arranged in a circle. It is made of an outer transparent ring and an inner filled ring.
Besides the inner ring, there is an unordered list designed to partition the outer ring in 8 sections and the aforementioned links to various websites.

With the help of css code, items in the unordered list change color when hovered over, though hovering over the links within sectors will cause the sector to switch back to its original color.



## CSS Content
CSS classes referring to header and footer elements will not be explained here, as these can be found in Wordpress documentation.

What will mainly be discussed here is code relating to the circular arrangement of website links in the body content of each webpage.

Each section of the circle is defined by its own class under .slice and .slice-contents, affecting its position within the circle.
.slice-contents adjusts the appearance of each sector, while .slice adjusts the position of the whole list as a circle within its parent div defined under .circle-container-outer
Uniformity was strived to be maintained but ultimately could not be achieved as link text tended to be variable in length, which called for manual adjustment of style code within the html body.
Padding was adjusted to ensure that the presentation of text within the circle was as uniform as possible among the various webpages.

The links within the circle are defined under .degXXX, where XXX refers to the angle of rotation relative to the right radius of the circle.
Padding and other text formatting is defined here, though some cases called for overriding these attributes within the html body.



## Plugins
Fullwidth Page Templates and Ivory Search were used to adjust the body content and the header search bar, respectively.
FW Fullwidth was used as the page attribute for each webpage in the site. This allows the body content to stretch to the full width of the viewport.