# Baidu Activity prediction

These are two of the Baselines of the Baidu activity prediction project. The project structure is explained as follows:

* data: Source data and processed data
* data_pre_process: Preprocess the source data

* DataLoader: Responsible for data loading and fine-grained processing
* Model:Baseline model
* config: Model parameters
* main.py and run.py: Model train and test

## Environment Create

sh env_create.sh

## Run
python main.py

## References

* LSCNN: https://github.com/chantcalf/2018-Rank4-  choose NN1 model
* RNN: https://github.com/drop-out/RNN-Active-User-Forecast
