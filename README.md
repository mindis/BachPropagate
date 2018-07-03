0)Get track background data from spotify, create necessary pkls
1)Create splits: a)BG750 b)train c)test d)challenge(provided) e)telescoping
2)Generate pkl where necessary-> pkl for trackfeatures and details; pid track mapping; splits pkls; most popular tracks
3)clean the titles, *provide stop list *provide synonyms list, bigrams
4)create background index documents, script to generate docs; config file to create indexes. 3 indexes -> Meta1, Meta2 and PRFQE
5)create queries for these indexes for train, test and challenge
4)script to generate results for the queries
5)script to parse these results 2 different formats(BM25 vs QE)
6)script to generate various metapaths and w2v models on BG 750 playlists;4 CBOW models ->a)just playlists, b)playlists and titles interspersed, c)AILA, d)ILI  
7)for each query playlist in splits, get 1000 items for the plalyist representation; batch generate and save
8)main track: generate training data [PRFQE+BM25-1+BM25-2 -> 2000 items]+trackfeatures+playlist features+track-playlistfeatures+w2v features
9)main track: generate test data(and challenge data)
10)param sweep script to find right lambda mart model [train, test and evaluate]
11)creative track: generate training data [PRFQE+BM25-1+BM25-2 -> 2000 items]+trackfeatures+playlist features+track-playlistfeatures+w2v features+track features from spotify api --> -missingzero
12)run built model on  challenge data
13)prepare submission(popular items when playlist size <500)