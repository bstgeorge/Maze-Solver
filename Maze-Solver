let maze = [
  'X XXXXXXXXXXXXXXXX',
  'X XXXXXXXX     XXX',
  'X          XXXXXXX',
  'XXXXX XXXXXXXXXXXX',
  'XX         XXXXXXX',
  'XXXXXXXXXX XXXXXXX',
  'X    XXXXX X     X',
  'XXXX XXXXX       X',
  'XXX        X     X',
  'XXXEXXXXXXXXXXXXXX'
];

let start = {
  x: 1,
  y: 0
}

let path = [];

let x_max = maze[0].length;
let y_max = maze.length;


let seen = [];
for (let i = 0; i < y_max; i++ ) {
  seen.push(Array(x_max).fill(0))
}


let move = [
  [0, 1],
  [1, 0],
  [0, -1],
  [-1, 0]
]


let solveMaze = (maze, seen, currentX = start.x, currentY = start.y) => {

  // console.log(`@ (${currentX}, ${currentY})`)

  // base cases

  // outside boundary of maze
  if (currentY < 0 || currentY >= y_max || currentX < 0 || currentX >= x_max) {
    // console.log('exceeded boundary');
    return false;
  }

  // hit wall
  if (maze[currentY][currentX] === 'X') {
    // console.log('hit wall');
    return false;
  }

  // already seen
  if (seen[currentY][currentX] === 1) {
    // console.log('space already visited');
    return false;
  }
  // found end
  if (maze[currentY][currentX] === 'E') {
    // console.log('success');
    path.push({
      x: currentX,
      y: currentY
    })
    return true;
  }



  // set current position to seen
  // console.log('successful blank space')
  seen[currentY][currentX] = 1;

  // recurse
  for (let i = 0; i < move.length; i++) {
    // currentX = currentX + move[i][0];
    // currentY = currentY + move[i][1];
    path.push({
      x: currentX,
      y: currentY
    })
    let found = solveMaze(maze, seen, currentX + move[i][0], currentY + move[i][1]);
    if (found) {
      return path;
    } else {
      path.pop();
    }
  }
}

solveMaze(maze, seen)
for (let i = 0; i < path.length; i++) {
  console.log(path[i]);
}
