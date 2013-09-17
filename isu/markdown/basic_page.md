<img class="logo" src="../images/IXM-Transparent-Vertical.jpg" style="float:right; margin:-10px 15px 0 0;" height="90" />
<img class="logo" src="../images/isu_logo.png" alt="Indiana State University logo" />

# Creating a Basic Page

1. [Login](#login)
2. [Create Basic Page](#create-basic-page)
3. [Create title](#create-title)
4. [Copy content to be migrated](#copy-content-to-be-migrated)
5. [Paste into Body field and clean up](#paste-into-body-field-and-clean-up)
6. [Add Primary Topic](#add-primary-topic)
7. [Choose a URL alias](#choose-a-url-alias)
8. [Add to main menu](#add-to-main-menu)
9. [Save](#save)
10. [Publish](#publish)

## Login

Navigate to the site and login by going to /user. For instance, if the site is located at www.test.com, you would navigate to www.test.com/user.

## Create Basic Page

In the admin menu bar hover over the "Content" menu item and scroll down to "Add Content", and then over to "Basic Page".

![alt text](http://dl.dropbox.com/u/57694/Screenshots/-97j.png "Create Basic Page")

This will open the Basic Page creation form.


## Create title

Create a title for the page in the "Title" field. This title will be used to display the content, and also to find the content in the administrative content listing interface.


## Copy content to be migrated

Copy the content from the old site in preparation for entering it into the Basic Page form. This can be done in a variety of ways, and will likely change depending on the particular page being migrated. One way is just to copy the plain text and paste it into the [wysiwyg](https://en.wikipedia.org/wiki/WYSIWYG) editor in the Basic Page form.

Sometimes this isn't ideal, for instance if you want to preserve the actual html markup on the source page. When I want to preserve the markup, I will instead copy it. The technique I usually use is to inspect the html in the browser's developer tools. In Chrome it can look something like this:

Right-click on the content you want to copy and select "Inspect element"

![Chrome inspect element context menu](http://dl.dropbox.com/u/57694/Screenshots/udl~.png "Inspect element")

When the "Elements" tab in developer tools opens, I find the parent html element of the content I want to copy and I right-click to select "Copy as HTML"

![Copy markup from developer tools](https://dl.dropboxusercontent.com/u/57694/Screenshots/1ghs.png "Copy as HTML")


## Paste into Body field and clean up

Paste your content into the "Body" field in the Basic Page form. When using the wysiwyg you can paste the plain text or formatted content and then edit it using the editor buttons.

![Paste content in wysiwyg mode](http://dl.dropbox.com/u/57694/Screenshots/9wnt.png "Paste content in wysiwyg mode")

Sometimes you'll want more control over the markup. In this case, you'll want to select the "Switch to plain text editor" link below the editor field to exit the wysiwyg and go straight to a plain text mode that allows you to enter html directly. When using the approach described above to copy content as html, you'll want to paste it into the field after you've selected plain text editor mode.

![Paste html in plain text mode](http://dl.dropbox.com/u/57694/Screenshots/m_w~.png "Paste html in plain text mode")

Once you've pasted the content in, either in the wysiwyg editor or directly as html in the plain text editor, you'll most often need to do some clean up. When pasting html in plain text mode, you should remove any custom classes that were being used on the old site for styling purposes. You should also seek to improve the html by removing unnecessary br elements and striving to make the markup as semantic as possible. Perhaps most importantly, you should remove any inline styling so that the site's styles can remain consistent.

![Clean up html](http://dl.dropbox.com/u/57694/Screenshots/o1xx.png "Clean up html")


## Add Primary Topic

Add appropriate terms in the "Primary Topic" field. This field uses something called a taxonomy to categorize content across the site. This helps us to display related content in various places in the site. By "tagging" this particular page, it can help to organize the site and surface relevant content being created here elsewhere when appropriate.

The taxonomy that this field uses is a controlled vocabulary, meaning that you cannot enter your own tags here, but rather have to select from the already available tags. You can add new primary topics/tags to the vocabulary, but it has to be done elsewhere.

![Select primary topic/s](https://dl.dropboxusercontent.com/u/57694/Screenshots/mzcd.png "Select primary topic/s")


## Choose a URL alias

In the metadata section at the bottom of the form, enter the correct url alias for the page based on your sitemap. The url alias is what determines the path where the page will be located. In Drupal, all pieces of content have system paths. These system paths can then be aliased to create a new path for that content that you can define. The system paths for ordinary content like a Basic Page are /node/[node id]. Each new piece of content is called a "node" and each node has a unique identifying integer id. For example, the first piece of content created in any site will have a system path of /node/1.

Aliases are automatically generated by default, so you'll need to uncheck the "Generate automatic url alias" checkbox to allow your own manually defined alias to take effect.

![Manually enter url alias](http://dl.dropbox.com/u/57694/Screenshots/038s.png "Manually enter url alias")


## Add to main menu

Ordinarily when you're creating a Basic Page, that page belongs somewhere in the overall sitemap. As a result, it needs to be placed in the main menu for the site. This menu contains all components of the site's hierarchy. Where the item is placed in the site's hierarchy should be directly correlated to the url alias chosen for the page. For example, a page located at

/about/fastfacts

should be placed as a first child of the "About" page (/about) in the menu. You select the page's location by selecting the appropriate parent page from the "Parent item" select element.

![Place the page in the main menu](http://dl.dropbox.com/u/57694/Screenshots/_wzj.png "Place the page in the main menu")


## Save

Save the form as a draft. This means that it is not published and is not available to the public, but all of your changes are preserved.

## Publish

Once all revisions are complete and you're ready to publish the page to the public, go back into the edit form and select from the "Publishing options" tab in the metadata section at the bottom. Change the "Moderation state" to "Published".

![Publish the page](http://dl.dropbox.com/u/57694/Screenshots/05fr.png "Publish the page")






