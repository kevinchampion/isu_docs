<img class="logo" src="../../global_assets/images/IXM-Transparent-Vertical.jpg" style="float:right; margin:-10px 15px 0 0;" height="90" />
<img class="logo" src="../assets/images/isu_logo.png" alt="Indiana State University logo" />

<a href="index.html">Home</a>

# Faculty Profiles - Technical Document

* [Import Process](#import-process)
* [Fields](#fields)
* [Faculty Images](#faculty-images)
* [Syncing User to Profile](#syncing-user-to-profile)
* [Troubleshooting](#troubleshooting)

## Import Process

Every night, ISU exports faculty data to the following location on the web server `/home/ccidman`

At **2:00 am**, a Jenkins job copies all files located in the `/home/ccidman` directory to the `/sites/default/files/feeds` directory. At **3:00 am**, elysia_cron kicks off the isu_faculty_cron job which triggers the Feeds importer 'staff_profiles'. Faculty profiles are then updated in batches based on the job_scheduler cron job.

![Import](../assets/images/FacultyImport.png "Faculty Import")

## Fields


The faculty profile fields that are updated during isu_faculty_cron are followed below. Fields that have custom modifications have explainations provided.

* **title**: the field_first_name and field_last_name create the title
* **field_name_prefix**
* **field_first_name**
* **field_middle_name**
* **field_last_name**
* **field_name_suffix**
* **field_job_title**
* **field_id**
* **field_pidm**
* **field_email**
* **field_office**
* **field_telephone**: the output of this field has hard-coded area code and three digit prefix if needed.
* **field_banner_image**: This field is populated by using ISU's image API which is currently in a development state and may be updated. An updatable setting has been added to allow site admins to update the url of the image API in the event that ISU updates their endpoint url. See [here](#faculty-images) for more information.
* **field_faculty_department_banner**: This taxonomy term_reference has two fields which are used to group data for external use: field_parent_organization and field_faculty_department. These fields are not saved on the faculty content, they are saved in the taxonomy term object.

## Faculty Images

### How images are imported
During the faculty profile import, the image file associated with it is downloaded from the ISU image API by accessing the following url:

`https://jas.indstate.edu/DisplayBlobServlet/?pidm=[id]`.

The file is saved to the database using a custom function **_file_save_external()**. Because the image format is originally saved in a TIFF format, it is converted to PNG by using the PHP extension ImageMagick. This is also done in the _file_save_external() function.

## Syncing User to Profile

![LDAP](../assets/images/FacultyLDAPLogin.png "LDAP")

When a user logs in, the LDAP module attempts to sync the Drupal user to an LDAP user. If an LDAP sync is successful, the isu_faculty module will attempt to sync the user to a faculty profile. If successful, the user is given the 'faculty' role and assigned owner of their respective faculty profile node.

## Troubleshooting
Here are a list of potential problems that may arise in the future.

* Faculty profiles aren't updating/importing
	* Verify that ISU is still updating the files in /home/ccidman
	* Verify that the Jenkins job is updating /default/files/feeds
	* Verify that the file name is correct on /admin/config/people/isu_faculty
* SSO is not working
	* Check the dblog for ldap errors	 	
	* If error log doesn't reveal obvious answer, test LDAP connection by going to /admin/config/people/ldap/servers/test/isu and clicking **Test** 
	* If the test returns LDAP data, you know that an LDAP connection is being made. If not, there is a problem connecting to the LDAP server.
* Faculty images are not updating
	* Connect to the ISU VPN and manually typing in the url (found here: /admin/config/people/isu_faculty) with a real PIDM number. 
	* If no image is loaded from the url, you will know to contact ISU to get further information