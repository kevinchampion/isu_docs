<img class="logo" src="../../global_assets/images/IXM-Transparent-Vertical.jpg" style="float:right; margin:-10px 15px 0 0;" height="90" />
<img class="logo" src="../assets/images/isu_logo.png" alt="Indiana State University logo" />

# Banner Slides

1. [Intro](#intro)
2. [Creating](#creating)
3. [Styles](#styles)
4. [Updating](#updating)

## Intro

Banners are a type of "Media Asset" that can be created while you are adding or updating a page or other content of the site. Banners are re-usable which means you can use the same banner on multiple pages without having to re-create the banner. When you add more than one banner to a page, it creates a slide-show display.

## Creating

You'll more than likely create a new banner while creating a page. Here are the steps to create one.

### Step 1

Create a page by navigating through the administration menu and select:

	Content > Add content > Page.

There are two buttons at the top of the 'Create Page' form: 

**'Add new Media Asset'** and **'Add existing Media Asset'**

Since we want to create a new Media Asset (Banner), click:

**'Add new Media Asset'**

![Add Banner Step 1](../assets/images/AddBanner1.png "Adding Banner Step 1")

### Step 2

The 'Add New Media Asset' dialog will appear. The first thing you'll want to do is **Select** an **Image**

![Add Banner Step 2](../assets/images/AddBanner2.png "Adding Banner Step 2")

### Step 3

Click **Browse** to locate an image on your computer.

Once you've selected an image on your computer, click **Upload** to upload your image from your computer.
 
![Add Banner Step 3](../assets/images/AddBanner3.png "Adding Banner Step 3")

### Step 4

Click **Next** to save the image to this banner.

![Add Banner Step 4](../assets/images/AddBanner4.png "Adding Banner Step 4")

### Step 5 

![Add Banner Step 5](../assets/images/AddBanner5.png "Adding Banner Step 5")

![Add Banner Step 6](../assets/images/AddBanner6.png "Adding Banner Step 6")

![Add Banner Step 7](../assets/images/AddBanner7.png "Adding Banner Step 7")

![Add Banner Step 8](../assets/images/AddBanner8.png "Adding Banner Step 8")

![Add Banner Step 9](../assets/images/AddBanner9.png "Adding Banner Step 9")

![Add Banner Step 10](../assets/images/AddBanner10.png "Adding Banner Step 10")

![Add Banner Step 11](../assets/images/AddBanner11.png "Adding Banner Step 11")

![Add Banner Step 12](../assets/images/AddBanner12.png "Adding Banner Step 12")

![Add Banner Step 13](../assets/images/AddBanner13.png "Adding Banner Step 13")

![Add Banner Step 14](../assets/images/AddBanner14.png "Adding Banner Step 14")

![Add Banner Step 15](../assets/images/AddBanner15.png "Adding Banner Step 15")

![Add Banner Step 16](../assets/images/AddBanner16.png "Adding Banner Step 16")

![Add Banner Step 17](../assets/images/AddBanner17.png "Adding Banner Step 17")

![Add Banner Step 18](../assets/images/AddBanner18.png "Adding Banner Step 18")

### Title

The title field of the node is for internal administrative use only.

![Administrative title field](../assets/images/1tv7.png "Administrative title field")

### Image

The image field is for uploading the actual banner image.

![Banner image field](../assets/images/qztv.png "Banner image field")

### Link

The link field is for applying a link to the entire banner overlay area. If a link is not present, the overlay will not link anywhere. This is different than the previous caption technique which only linked content within the separate caption field.

![Link field](../assets/images/k_gm.png "Link field")

### Overlay title

The banner overlay content comes from the "Overlay title" field. This field has a number of token replacements for building the textual overlay content. In essence, these tokens are replaced by html elements with classes that allow for targeting the elements using css selectors in order to style them. The description of the field describes the token options and gives examples of how to use them.

![Overlay title field](../assets/images/9bkz.png "Overlay title field")

With the new changes, the caption field content should be placed inside the [caption] token wrapper. For the "page" style overlay, the [last] token wrapper should be placed around the last word in the overlay title in order to change the text color of the last work to match the design specification.

### Overlay position

The overlay position field determines whether the overlay will be aligned on the left or right side of the banner image.

![Overlay position field](../assets/images/lral.png "Overlay position field")

### Overlay vertical align

The overlay vertical align field determines the vertical placement of the overlay within the banner image area. This uses the "vertical-align" css property and the value of this field should be a percentage.

![Overlay vertical align field](../assets/images/0jkk.png "Overlay vertical align field")

### Overlay style

The overlay style determines which style overlay will be used. The "home" style features the Arvo font and has all white text and lines with a tight padding and margin. The "page" style features the Helvetica font and has light blue features and a salmon colored title text color with wider padding and margins.

![Overlay style field](../assets/images/~o1b.png "Overlay style field")

The original site launch contained only one banner slider style and contained a separate caption field for writing the textual caption beneath the main text overlay section.

## Styles

### Home style

![Home banner style](../assets/images/-nu9.png "Home banner style")

### Page style

![Page banner style](../assets/images/g6q4.png "Page banner style")

## Updating

## How it works

The slide nodes require an image and a textual message for the banner overlay.



## Add a new banner slider

The process of adding a new banner slider, that is an entirely new slideshow for placement in a new section of the site, requires three steps.

1. A new nodequeue must be created
2. A new view display must be created
3. The new block must be placed with appropriate visibility settings

### Nodequeue

In order to control which slides will be used and what order they'll display in, a new nodequeue must be created. From /admin/structure/nodequeue select "Add simple queue":

![Add queue](../assets/images/-evf.png "Add queue")

Fill out the configuration form for creating the new queue and make sure to restrict the content type to only allow "Slide" nodes to be added to the queue.

### View display

In order to render the slides in the nodequeue as a slideshow, a views block display is used. From /admin/structure/views/view/homepage_slider/edit review the view that renders the slideshows. Clone the homepage slider display and then modify the titles and options of the new display to match the subject of your new slider.

![Clone display](../assets/images/gk83.png "Clone display")

After cloning the display, the most important detail that must be changed is configuring the relationship to use the new nodequeue. In the "advanced" column under the "Relationship" heading, select the "Nodequeue: Queue" item.

![Nodequeue relationship](../assets/images/2x65.png "Nodequeue relationship")

Within the configuration settings window, change the setting to limit the results to the new Nodequeue that you created in the step above. If this isn't changed, the new views display will render the items from a different Nodequeue.

![Choose correct queue](../assets/images/y-i7.png "Choose correct queue")

Save the configuration and the view.

### Block placement

When you saved the new view display, it automatically generated a new block on the block placement configuration page located at /admin/structure/blocks. Find the newly created block, configure its visibility settings to restrict it to only display when and where you need it to, and place it in the "Banner" region.

