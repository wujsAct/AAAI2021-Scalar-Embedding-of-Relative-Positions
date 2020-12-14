#download SQuAD and Glove
bash download.sh

#preprocess the data
python raw_config.py --mode prepro

#to train and test raw (TPE)
bash raw-run-v1.sh  

(python config-v1.py --mode test)
(python config-v1.py --mode train)

#to train and test T5
bash t5-run-v1.sh
bash t5-nob-run-v1.sh

#to train and test AT5 (soft-t5)
bash soft-t5-run-v1.sh
bash soft-t5-nob-run-v1.sh


#get prior score
cd ret/
python att_analysis.py