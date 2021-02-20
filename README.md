# UNREAL + Auxiliary Selection
深層強化学習手法であるUNREALにおいて，補助タスクを適応的に選択するAuxiliary Selectionを導入した手法のコードである．

このコードは，[UNREALのコード](https://github.com/miyosuda/unreal)をもとに書き換えたコードである．

## Training
***UNREALの場合***
```
cd ~/RL-AuxiliaryTask-Selection/code/lab/unreal/
python main.py
```

``options.py``にてハイパーパラメータを変更することが可能である．
以下に主なハイパーパラメータを示す．

- ``env_name``: ゲーム名(nav_maze)
- ``use_pixel_change``: 補助タスクPixel Controlの有無 (True or False)
- ``use_value_replay``: 補助タスクValue Function Replayの有無 (True or False)
- ``use_reward_prediction``: 補助タスクReward Predictionの有無 (True or False)
- ``parallel_size``: 分散学習時のworker数
- ``max_time_step``: global step数

``unreal_checkpoint``フォルダに学習済みモデルの保存，``unreal_log``フォルダにスコアの推移を記録したtensorbordのファイルが保存される．

***UNREAL+Auxiliary Selectionの場合***
```
cd ~/RL-AuxiliaryTask-Selection/code/lab/unreal-approch/
python main.py
```

UNREALの場合と同様に``options.py``にてハイパーパラメータの変更が可能である．

``unreal_checkpoint``フォルダに学習済みモデルの保存，``unreal_log``フォルダにスコアの推移を記録したtensorbordのファイルが保存される．

## Visualization
***UNREALの場合***
```
cd ~/RL-AuxiliaryTask-Selection/code/lab/unreal/
python display.py
```

***UNREAL+Auxiliary Selectionの場合***
```
cd ~/RL-AuxiliaryTask-Selection/code/lab/unreal-approch/
python display.py
```

