# Overview structure of code

## Agent
- game
- model

Training:
- state = get_state(game)
- action = get_move(state):
    - model.predict()
- reward, game_over, score = game.play_step(action)
- new_state = get_state(game)
- remember
- model.train()

## Game(Pygame)
- play_step(action)
    -> reward, game_over, score

## Model(PyTorch)
Linear_QNet(DQN)
- model.predict(state)
    -> action


# Later section
## Reward
- eat food: +10
- game over: -10
- else: 0

## Action
[1,0,0] -> straight
[0,1,0] -> right turn
[0,0,1] -> left turn


## state(11 values)
[danger state, danger right, danger left, direction left, direction right, direction up, direction down, food left, food right, food up, food down]