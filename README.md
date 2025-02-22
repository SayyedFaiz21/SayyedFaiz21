<!DOCTYPE html><html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Special Moments</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #f9f3e6;
            color: #333;
            padding: 20px;
        }
        h1 {
            color: #ff6f61;
        }
        .upload-container {
            margin: 20px;
        }
        .gallery {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
        }
        .gallery img {
            width: 200px;
            height: auto;
            margin: 10px;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        }
        .message {
            margin-top: 20px;
            font-size: 18px;
            font-weight: bold;
            color: #555;
        }
    </style>
</head>
<body>
    <h1>You're So Special!</h1>
    <p>Upload your favorite moments and add messages to make this page uniquely yours.</p><div class="upload-container">
    <input type="file" id="imageUpload" multiple accept="image/*">
    <input type="text" id="messageInput" placeholder="Add a sweet message...">
    <button onclick="addImage()">Upload</button>
</div>

<div class="gallery" id="gallery"></div>
<p class="message" id="message"></p>

<script>
    function addImage() {
        const gallery = document.getElementById('gallery');
        const message = document.getElementById('message');
        const input = document.getElementById('imageUpload');
        const messageInput = document.getElementById('messageInput');
        
        if (input.files.length > 0) {
            for (let file of input.files) {
                const reader = new FileReader();
                reader.onload = function(event) {
                    const img = document.createElement('img');
                    img.src = event.target.result;
                    gallery.appendChild(img);
                };
                reader.readAsDataURL(file);
            }
        }
        
        if (messageInput.value.trim() !== '') {
            message.innerText = messageInput.value;
        }
    }
</script>

</body>
</html>
