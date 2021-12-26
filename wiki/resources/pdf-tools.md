# PDF Tools

## Steps 

From [How to Convert Multiple Images to PDF in Ubuntu Linux](https://itsfoss.com/convert-multiple-images-pdf-ubuntu-1304/)

- First install imagemagick  
    ```
    sudo apt-get install imagemagick
    ```
- Then convert images to PDF
    ```
    convert image1.jpg image2.png image3.bmp output.pdf
    ```
- Or convert all files to one PDF
    ```
    convert * output.pdf
    ```

## Issues

- ImageMagick security policy 'PDF' blocking conversion  

    From https://stackoverflow.com/questions/52998331/imagemagick-security-policy-pdf-blocking-conversion  

	Add
    ```
    <policy domain="coder" rights="read | write" pattern="PDF" />
    ```
	just before `</policymap>` in `/etc/ImageMagick-7/policy.xml`
	
	
- PDF quality when converted

    From https://legacy.imagemagick.org/discourse-server/viewtopic.php?t=8707  
    ```
    convert -density 1200 page.pdf  -resample 300  page.jpg
    ```
