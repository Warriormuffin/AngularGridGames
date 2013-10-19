# Angular Grid Games

An angular directive and small framework for quickly designing 2d grid based board games. This is a work in progress. The first game example Othello is playable. The basic idea is that the directive will manage the board, and it's tokens but the play dynamic of each token and the scoring can be handled in a controller specific to that game. 

## Usage

Currently you need to include grid_board_games.js and the controller for the games you would like to use (othello_game_board_controller.js, chess... et). All styles and layout are handled through css. The directive applies minimal classes to the layout. 

## Here is an example usage
```html
<div class='gameContainer' ng-controller='OthelloGameBoardController'>
    <div ng-game-board cols='8' rows='8' ng-model='gameBoard'></div> 
    <ul>
      <li>{{ activePlayer().name }} it's your move </li>
      <li ng-repeat='player in players'>
        <span class='{{player.token}}Token'>{{player.name}}: </b> {{player.score}}
      </li>
     </ul>

     <select ng-model='firstPlayer' ng-options='player.name for player in players'></select>
    
     <button ng-click='newGame()'/>New Game</button>
     {{ gameStatus }}
 </div>

```

##which generates the following grid and playable game
![alt tag](https://www.evernote.com/shard/s283/sh/a4b2c9b2-ae52-4cb5-b191-1148d2c4ee5c/d3c86de39c8dd9a6a60d4209e391e96b)

##TODO
 * Add Tests
 * Other Games (Chess, Go, Pente, Peg Solitaire)
 * Get a demo on gh-pages branch
