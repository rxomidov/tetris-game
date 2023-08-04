# Tetris
A vanilla javascript game. Source code: kubowania.

<h2>Brief</h2>
 
* The game should stop if a Tetrimino fills the highest row of the game board
* The player should be able to rotate each Tetrimino about its own axis
* If a line is completed it should be removed and the pieces above should take its place
* Render a grid-based game in the browser
* Include separate HTML / CSS / JavaScript files
* Use Javascript for DOM manipulation
* Deploy your game online, using Github Pages, where the rest of the world can access it
* Use semantic markup for HTML and CSS (adhere to best practices)

<h2>Technologies Used</h2>

* HTML5
* CSS3
* JavaScript
* Git
* GitHub
* Google Fonts

<h2>Features piece of code no.1</h2>

```
//freeze the shape
  function freeze() {
    // if block has settled
    if(current.some(index => squares[currentPosition + index + width].classList.contains('block3') || squares[currentPosition + index + width].classList.contains('block2'))) {
      // make it block2
      current.forEach(index => squares[index + currentPosition].classList.add('block2'))
      // start a new tetromino falling
      random = nextRandom
      nextRandom = Math.floor(Math.random() * theTetrominoes.length)
      current = theTetrominoes[random][currentRotation]
      currentPosition = 4
      draw()
      displayShape()
      addScore()
      gameOver()
    }
  }
  freeze()

```

<h2>Features piece of code no.2</h2>

```
  //Add score
  function addScore() {
    for (currentIndex = 0; currentIndex < 199;currentIndex += width) {
      const row = [currentIndex,currentIndex+1,currentIndex+2,currentIndex+3,currentIndex+4,currentIndex+5,currentIndex+6,currentIndex+7,currentIndex+8,currentIndex+9]
      if(row.every(index => squares[index].classList.contains('block2'))) {
        score += 10
        lines +=1
        scoreDisplay.innerHTML = score
        linesDisplay.innerHTML = lines
        row.forEach(index => {
          squares[index].style.backgroundImage = 'none'
          squares[index].classList.remove('block2') || squares[index].classList.remove('block')

        })

```