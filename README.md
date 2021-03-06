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

- ``env_name``: ゲーム名
  - nav_maze_static_0{1,2,3}
  - nav_maze_random_goal_0{1,2,3}
  - seekavoid_arena_0{1,2,3}
  - lt_horseshoe_color
  - stairway_to_melon
  - lt_chasm
  - lt_hallway_slope
  - lt_space_bounce_hard etc.
- ``use_pixel_change``: 補助タスクPixel Controlの有無 (True or False)
- ``use_value_replay``: 補助タスクValue Function Replayの有無 (True or False)
- ``use_reward_prediction``: 補助タスクReward Predictionの有無 (True or False)
- ``parallel_size``: 分散学習時のworker数
- ``max_time_step``: global step数

``unreal_checkpoints``フォルダに学習済みモデルの保存，``unreal_log``フォルダにスコアの推移を記録したtensorbordのファイルが保存される．

***UNREAL+Auxiliary Selectionの場合***

```
cd ~/RL-AuxiliaryTask-Selection/code/lab/unreal-approch/
python main.py
```

UNREALの場合と同様に``options.py``にてハイパーパラメータの変更が可能である．

``unreal_checkpoints``フォルダに学習済みモデルの保存，``unreal_log``フォルダにスコアの推移を記録したtensorbordのファイルが保存される．

## Visualization

***UNREALの場合***

```
cd ~/RL-AuxiliaryTask-Selection/code/lab/unreal/
python display.py
```

training時と同様に``options.py``にてハイパーパラメータの変更が可能である．

``options.py``内の``checkpoint_dir``を可視化したいモデルが存在するフォルダのパスとする．
読み込むモデルの指定は，``unreal_checkpoints``フォルダ内に作成される``checkpoint``ファイルに記述することで指定している．

***UNREAL+Auxiliary Selectionの場合***
```
cd ~/RL-AuxiliaryTask-Selection/code/lab/unreal-approch/
python display.py
```

モデルのパス等は，UNREALの場合と同様である．

## Trained models

過去の実験での学習済みモデルは，modelフォルダ内にある．

modelフォルダ内のディレクトリ構造は以下の通りである．

model

  ├ Auxiliary-Selection (Auxiliary Selectionを導入したモデル)
  
  │    └ 各ゲームでのモデルのフォルダ
  
  │          └ 学習step数毎でのモデルのフォルダ
  
  └ Auxiliary-Tasks (各補助タスクの組み合わせによるモデル)
  
       └ 各ゲームでのモデルのフォルダ
  
             └ 学習step数毎でのモデルのフォルダ
