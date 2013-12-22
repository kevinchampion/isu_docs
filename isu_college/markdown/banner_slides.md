<img class="logo" src="../../global_assets/images/IXM-Transparent-Vertical.jpg" style="float:right; margin:-10px 15px 0 0;" height="90" />
<img class="logo" src="../assets/images/isu_logo.png" alt="Indiana State University logo" />

# Banner Slides

1. [Intro](#intro)
2. [Creating Banners](#creating-banners)
3. [Banner Styles](#banner-styles)
4. [Updating Banners](#updating-banners)

## Intro

Banners **appear at the top of pages** that enable this feature.

Banners are a **"Media Asset"** that can be created while you are adding or updating a page or other content of the site. 

**Banners are re-usable** which means you can use the **same banner on multiple pages** without having to re-create the banner. 

When you **add multiple banners** to a single page, it creates a **slide-show display.**

## Creating Banners

You'll more than likely create a new banner while creating a page. Here are the steps to create one.

### Step 1

Create a page by navigating to the following in the administration menu:

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

Once you've selected an image on your computer, click **Upload** to upload the image.
 
![Add Banner Step 3](../assets/images/AddBanner3.png "Adding Banner Step 3")

### Step 4

Click **Next** to continue.

![Add Banner Step 4](../assets/images/AddBanner4.png "Adding Banner Step 4")

### Step 5 

Enter **Alt Text** and **Title Text** 

**Alt Text:** Displays when the image isn't loaded
**Title Text:** Displays when the image is hovered

Click **Save** to finish saving the image to this banner.

![Add Banner Step 5](../assets/images/AddBanner5.png "Adding Banner Step 5")

### Step 6

After you've saved an image, it should appear above the **Title** field.

Next, enter a **Title** for this banner. The title field is only used for administrative purposes. **The title field is not shown on the banner.**

![Add Banner Step 6](../assets/images/AddBanner6.png "Adding Banner Step 6")

![Add Banner Step 7](../assets/images/AddBanner7.png "Adding Banner Step 7")

### Step 7 

The **Body** holds the *text overlay* of the banner.

Click the **DIV </>** button 

![Add Banner Step 8](../assets/images/AddBanner8.png "Adding Banner Step 8")

### Step 8

After clicking the **DIV </>** button, a popup will appear. 

On the left, select the **Style** of slideshow you want.

![Add Banner Step 9](../assets/images/AddBanner9.png "Adding Banner Step 9")

### Step 9

There are two Slideshow **Styles** 

**Left Slideshow Block** and **Right Slideshow Block**

Text on the banner will be aligned to the **left** or **right** respectively.

![Add Banner Step 10](../assets/images/AddBanner10.png "Adding Banner Step 10")

### Step 10

After selecting the Slideshow Style, your screen should look like this.

![Add Banner Step 11](../assets/images/AddBanner11.png "Adding Banner Step 11")

### Step 11

Change the text style to **Heading 2**

![Add Banner Step 12](../assets/images/AddBanner12.png "Adding Banner Step 12")

### Step 12

Select a **Formatting Style** to change the text looks.

![Add Banner Step 13](../assets/images/AddBanner13.png "Adding Banner Step 13")

In this example, we selected 'Large Line'

![Add Banner Step 14](../assets/images/AddBanner14.png "Adding Banner Step 14")

### Step 13

Start typing to see what the text looks like.

![Add Banner Step 15](../assets/images/AddBanner15.png "Adding Banner Step 15")

### Step 14

Once you are happy with the top line, press **Return/Enter** to start a new line. 

Click the **Formatting Styles** drop down to change the text style again.

In this case, we selected the 'Line Title' style.

![Add Banner Step 16](../assets/images/AddBanner16.png "Adding Banner Step 16")

### Step 15

Start typing to see the new style. 

![Add Banner Step 17](../assets/images/AddBanner17.png "Adding Banner Step 17")

### Step 17

Once you are satisfied with your banner overlay text, then click the **Create Media Asset** button.

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

![Styles](../assets/images/Styles1.png "Styles")

![Blue Line Style](../assets/images/BlueLine.png "Blue Line Style")

### Home style

![Home banner style](../assets/images/-nu9.png "Home banner style")

### Page style

![Page banner style](../assets/images/g6q4.png "Page banner style")

## Updating


