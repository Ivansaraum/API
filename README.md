# API

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Random Dog Images</title>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/css/bootstrap.min.css" rel="stylesheet">
  <style>
    body {
      text-align: center;
      margin-top: 50px;
    }
    img {
      max-width: 100%;
      height: auto;
      border-radius: 10px;
      margin-top: 20px;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1 class="mb-4">Random Dog Images</h1>
    <button id="fetchDog" class="btn btn-primary">Get a Random Dog</button>
    <div id="dogContainer" class="mt-4">
      <img id="dogImage" src="" alt="Random Dog Image" style="display:none;">
    </div>
  </div>

  <script>
    document.getElementById('fetchDog').addEventListener('click', () => {
      fetch('https://dog.ceo/api/breeds/image/random')
        .then(response => response.json())
        .then(data => {
          const dogImage = document.getElementById('dogImage');
          dogImage.src = data.message;
          dogImage.style.display = 'block';
        })
        .catch(error => console.error('Error fetching dog image:', error));
    });
  </script>
</body>
</html>
