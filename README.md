## Requirements

python==3.10.16
torch==2.4.0
numpy==1.26.4
gensim==4.4.0


## Run the Code

Go to the `src` folder in the `GRU4Rec` and `SASRec` or directory, then run the following commands. 

To save time, we provide the original pre-trained model, which is the first stage in the paper. The model can be loaded by running the commands and moving to the second stage to further improve the model performance using our method.


For `GRU4Rec`: 
```

On Beauty:
python main.py --data_name=Beauty --load_pretrain --model_idx=1 --dropout_prob=0.2 --rate_min=0.2 --rate_max=0.51 --contrast_tau=0.2

You are expected to get following results after training:
{'Epoch': 0, 'HIT@5': '0.0343', 'NDCG@5': '0.0221', 'HIT@10': '0.0545', 'NDCG@10': '0.0286', 'HIT@20': '0.0853', 'NDCG@20': '0.0364'}

On Sports_and_Outdoors:
python main.py --data_name=Sports_and_Outdoors --load_pretrain --model_idx=1 --dropout_prob=0.2  --n_pairs=2 --n_whole_level=3 --contrast_tau=0.1

You are expected to get following results after training:
{'Epoch': 0, 'HIT@5': '0.0187', 'NDCG@5': '0.0122', 'HIT@10': '0.0302', 'NDCG@10': '0.0159', 'HIT@20': '0.0476', 'NDCG@20': '0.0202'}

On Yelp:
python main.py --data_name=Yelp --load_pretrain --model_idx=1 --epochs=100 --start_valid=50 --dropout_prob=0.5 --contrast_tau=0.5

You are expected to get following results after training:
{'Epoch': 0, 'HIT@5': '0.0166', 'NDCG@5': '0.0104', 'HIT@10': '0.0287', 'NDCG@10': '0.0143', 'HIT@20': '0.0502', 'NDCG@20': '0.0197'}
```

For `SASRec`:
```

On Beauty:
python main.py --data_name=Beauty --model_idx=1 --load_pretrain --beta=0.4 --attention_probs_dropout_prob=0.1 --hidden_dropout_prob=0.1 --n_pairs=2 --n_whole_level=3 --rate_min=0.2 --rate_max=0.71

You are expected to get following results after training:
{'Epoch': 0, 'HIT@5': '0.0539', 'NDCG@5': '0.0370', 'HIT@10': '0.0804', 'NDCG@10': '0.0456', 'HIT@20': '0.1174', 'NDCG@20': '0.0549'}

On Sports_and_Outdoors:
python main.py  --data_name=Sports_and_Outdoors --model_idx=1  --load_pretrain --attention_probs_dropout_prob=0.1 --hidden_dropout_prob=0.1 --n_pairs=2 --contrast_tau=0.3 --n_whole_level=3 --rate_min=0.1 --rate_max=0.81

You are expected to get following results after training:
{'Epoch': 0, 'HIT@5': '0.0283', 'NDCG@5': '0.0186', 'HIT@10': '0.0449', 'NDCG@10': '0.0240', 'HIT@20': '0.0654', 'NDCG@20': '0.0292'}

On Yelp:
python main.py --data_name=Yelp --model_idx=1 --load_pretrain --epochs=100 --start_valid=50 --attention_probs_dropout_prob=0.1 --contrast_tau=0.3 --hidden_dropout_prob=0.1 --n_pairs=2 --n_whole_level=3 --beta=0.5

You are expected to get following results after training:
{'Epoch': 0, 'HIT@5': '0.0185', 'NDCG@5': '0.0117', 'HIT@10': '0.0329', 'NDCG@10': '0.0163', 'HIT@20': '0.0562', 'NDCG@20': '0.0222'}
```


## Log Files
We also provide log files on these three datasets in the `src/output` directory.


## Acknowledgement

Some models are implemented based on [BASRec](https://github.com/KingGugu/BASRec) and [RecBole](https://github.com/RUCAIBox/RecBole).

Thanks for providing efficient implementation.
