# ColorBox

https://0xr4z3r.github.io/ColorBox/.

This is the game of choosing color 
you can choose hard mode or easy mode using this function in JS:

function setupModeButtons(){

	//mode Buttons event listener 

	for(var i = 0; i < modeButtons.length; i++){
		modeButtons[i].addEventListener("click",function(){
		modeButtons[0].classList.remove("selected");
		modeButtons[1].classList.remove("selected");
		this.classList.add("selected");


		this.textContent === "Easy" ? numSquares = 3: numSquares = 6;
		// if(this.textContent === "Easy"){
		// 	numSquares = 3;
		// }else{
		// 	numSquares = 6;
		// }
		reset();
	});
  
  Then everytime every button is pressed we use this function to find out right answer:
  
  function setupSquares(){


	for(var i = 0; i < squares.length; i++){
	// add initial colors to squares
	squares[i].style.background = colors[i];

	//add click listeners to squares
	squares[i].addEventListener("click", function() {
		//grab color of clicked squares
		var clickedColor = this.style.background;
		//compare color to pickedColor
		if(clickedColor === pickedColor) {
			messageDisplay.textContent = "Correct!";
			resetButton.textContent = "Play Again?";
			changeColors(clickedColor);
			h1.style.background = clickedColor;
		} else {
			this.style.background = "#232323";
			messageDisplay.textContent = "Try Again";
		}
	});
}
}


reset function

function reset(){
	//generate all new colors
	colors = generateRandomColors(numSquares);
	//pick a new random color from array
	pickedColor = pickColor();
	//change colorDisplay to match picked Color
	colorDisplay.textContent = pickedColor;
	resetButton.textContent = "New Colors";
	//change colors of squares
	for(var i = 0; i < squares.length; i++) {
		if(colors[i]){
		squares[i].style.display = "block";	
		squares[i].style.background = colors[i];
	}else{
		squares[i].style.display="none";
	}
	}
	h1.style.background = "steelblue";
	message.textContent = "";
	this.textContent = "New Colors";
}


  
