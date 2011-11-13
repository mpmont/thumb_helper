**INSTALLATION GUIDE:**

1. Download the repository;

2. Copy thumb_helper.php to your ./application/helpers/ folder;

That's it, your good to go.

***

**USAGE:**

1. Loading the Helper

`$this->load->helper('thumb');`

**USING WITH UPLOAD LIBRARY:**

After uploading a image you have access to an simple array that has all the information about your image.

Like this:

`$image_data = $this->upload->data();`

Info on $image_data:

![array on $image_data](http://www.dropmocks.com/ihwep)

More information about this here: [Codeigniter/user_guide/libraries/file_uploading](http://codeigniter.com/user_guide/libraries/file_uploading.html)

For now you can pass 4 params to the thumb helper: 

1. Image data from upload;

2. Width

3. Height

4. Destination path

5. Maintain Aspect Ratio


like this:

`create_thumb($image_data, '100', '150', '.public/images/thumbs/', TRUE);`

Keep in mind that the 3rd param is optional. If only two params are passed to the thumb helper the thumb will resize the image maintaining the ratio. If theres a 3rd param then, by default the aspect ratio will not be maintained unless the 5th parameter is set to TRUE.

After the creation the thumb helper will return an array with the following content:

path -> The full path to the image;

thumb_marker -> The marker for the thumb, for now will always be equal to the thumb sizes that were passed to the thumb helper;

thumb_name -> The final name of the thumb;

I made this return in case someone needed to sent some of these values to the database for example.


**USING REMOTE FILE:**

For that insted of passing the array from image upload you can just pass the path to the file (including the file).

example:

`create_thumb('./public/images/myimage.jpg', '100', '150');`

***

**CHANGELOG**

**version 1.0.2**

* Added explicit option for maintaining aspect ratio when height and width are both specified

**version 1.0.1**

* Resize image from remote file;

* Added possibility to choose a different destination path;


**version 1.0**

* Resize image after upload with image data;

* Use just width or both width ad height;

* Return information about the thumbnail (path / thumb_marker / thumb_name )

***

**FUTURE FEATURES**

* Create crop functions;
