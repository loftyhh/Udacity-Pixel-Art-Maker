# Udacity-Pixel-Art-Maker
// Select color input
var color = document.getElementById('colorPicker');
// make the table that forms the canvas
var table = document.getElementById('pixelCanvas');
//make an event listener on sizePicker based on the height and width values to call the makeGrid function
var picker = document.getElementById('sizePicker');
picker.addEventListener('submit', function (event) {
  event.preventDefault();
  //input the values of height and width to make the grid
  var height = document.getElementById('inputHeight').value;
  var width = document.getElementById('inputWidth').value;
  makeGrid(height, width);
});

// When size is submitted by the user, call makeGrid()
function makeGrid(height, width) {
  // For Canvas design
  var table = document.getElementById('pixelCanvas');
  var tablebody = document.querySelector('tbody');
  // the makeGrid function
  if (tablebody !== null) {
    tablebody.remove();
    for (let x = 0; x < height; x++) {
      var row = table.insertRow();
      for (let y = 0; y < width; y++) {
        var cell = row.insertCell();
      };
    };
  }
  else {
    for (let x = 0; x < height; x++) {
      var row = table.insertRow();
      for (let y = 0; y < width; y++) {
        var cell = row.insertCell();
      };
    };
  };
  var newCells = document.querySelectorAll('td');
  for (var square of newCells) {
    //event listener to choose the color
    square.addEventListener('click', function draw() {
      var color = document.getElementById('colorPicker').value;
      this.style.backgroundColor = color;
    });
  };
};
