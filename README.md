<!DOCTYPE html>
<html>
<head>
    <title>Закодированная кликабельная картинка</title>
    <script type="text/javascript">
        function decodeImageAndRedirect() {
            // Закодированная строка изображения в формате base64
            var encodedImage = "iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVR42mNk+M9QDwADhgGAWjR9awAAAABJRU5ErkJggg==";

            // Декодирование строки изображения в формате base64
            var decodedImage = atob(encodedImage);

            // Создание объекта Blob из декодированной строки
            var arrayBuffer = new ArrayBuffer(decodedImage.length);
            var uint8Array = new Uint8Array(arrayBuffer);
            for (var i = 0; i < decodedImage.length; i++) {
                uint8Array[i] = decodedImage.charCodeAt(i);
            }
            var blob = new Blob([uint8Array], {type: 'image/png'});

            // Создание URL-адреса для объекта Blob
            var url = URL.createObjectURL(blob);

            // Создание нового окна или вкладки с URL-адресом изображения
            window.open(url);
        }
    </script>
</head>
<body>
    <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVR42mNk+M9QDwADhgGAWjR9awAAAABJRU5ErkJggg==" alt="Кликабельная картинка" onclick="decodeImageAndRedirect()" style="cursor: pointer;">
</body>
</html>
