## validates

| validate                   | helper                             |
| -------------------------- | ---------------------------------- |
| 必須データがはいっているか | validates :foo, presence: true     |
| 数値が期待通りか           | validates :foo, numaricality: true |
| 数値範囲が期待通りか       | validates :foo, inclusion: [ in: ]                                   |
