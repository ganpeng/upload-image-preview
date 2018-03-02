# upload-image-preview
upload-image-preview

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
    .fileinput-button {
        position: relative;
        display: inline-block;
        overflow: hidden;
    }

    .fileinput-button input {
        position: absolute;
        right: 0px;
        top: 0px;
        opacity: 0;
        -ms-filter: 'alpha(opacity=0)';
        cursor: pointer;
    }
    </style>
</head>

<body>
    <div class="fileinput-button">
        <span>上传</span>
        <input type="file" class="file-input" name="file">
    </div>
    <img src="" alt="" id="img">
    <script>
    (function() {

        var fileInput = document.querySelector("input[name=file]");
        var img = document.querySelector("#img");

        fileInput.addEventListener("change", function(e) {
            var file = e.srcElement.files[0];
            var blob = new Blob([file], { type: file.type })
            var reader = new window.FileReader();
            reader.readAsDataURL(blob);
            reader.onloadend = function() {
                base64data = reader.result;
                img.setAttribute("src", base64data);
            }
        }, false)


    })();
    </script>
</body>

</html>

```
