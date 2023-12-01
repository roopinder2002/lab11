# lab11
<!DOCTYPE html>
<html lang="en-us">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Shopping List Example</title>
    <style>
      body {
        font-family: Arial, sans-serif;
        background-color: #f4f4f4;
        margin: 0;
        padding: 0;
        box-sizing: border-box;
      }

      h1 {
        text-align: center;
        color: #333;
      }

      div {
        text-align: center;
        margin-bottom: 20px;
      }

      label {
        font-size: 16px;
        color: #555;
        margin-right: 10px;
      }

      input {
        padding: 8px;
        font-size: 14px;
      }

      button {
        padding: 8px 16px;
        font-size: 14px;
        background-color: #4caf50;
        color: #fff;
        border: none;
        cursor: pointer;
      }

      button:hover {
        background-color: #45a049;
      }

      ul {
        list-style-type: none;
        padding: 0;
        margin: 0;
      }

      li {
        margin-bottom: 10px;
        background-color: #fff;
        padding: 10px;
        border-radius: 5px;
        box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
        display: flex;
        justify-content: space-between;
        align-items: center;
      }

      li span {
        flex-grow: 1;
        margin-right: 10px;
      }

      li button {
        padding: 6px 12px;
        font-size: 12px;
        background-color: #e74c3c;
        color: #fff;
        border: none;
        cursor: pointer;
      }

      li button:hover {
        background-color: #c0392b;
      }
    </style>
  </head>
  <body>

    <h1>My Shopping List</h1>

    <div>
      <label for="item">Enter a new item:</label>
      <input type="text" name="item" id="item">
      <button>Add item</button>
    </div>

    <ul></ul>

    <script>
      const list = document.querySelector('ul');
      const input = document.querySelector('input');
      const button = document.querySelector('button');

      button.addEventListener('click', () => {
        const myItem = input.value;
        input.value = '';
        const listItem = document.createElement('li');
        const listText = document.createElement('span');
        const listBtn = document.createElement('button');
        listItem.appendChild(listText);
        listText.textContent = myItem;
        listItem.appendChild(listBtn);
        listBtn.textContent = 'Delete';
        list.appendChild(listItem);
        listBtn.addEventListener('click', () => { list.removeChild(listItem); });
      });
    </script>

  </body>
</html>
