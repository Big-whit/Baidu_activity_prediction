# Baidu Activity prediction

These are two of the Baselines of the Baidu activity prediction project. The project structure is explained as follows:

* **data**: Store processed data
* **Source_data**: Store source data (Source data has been uploaded)
* **data_pre_process**: Preprocess the source data
* **DataLoader**: Responsible for data loading and fine-grained processing
* **Model**: Baseline model (RNN and LSCNN)
* **config**: Model parameters
* **main.py** and **run.py**: Model train and test

## Environment Create

sh env_create.sh

## Model structure

### RNN

We use single-layer RNN structure，and the user's behavior information (without feature extraction) is used as the input of the model. Its dimension is [batch_size, seq_length, input_size] (see config and main for specific parameters). The hidden state of the last cell is output through the linear layer, as the predicted result

The loss function part adopts BCE and MSC models, which are determined according to specific evaluation indicators

### LSCNN

The LSCNN model is divided into two parts for fusion. The first part used embedded + LSTM, and the second part used CNN + LSTM. The first part is to embed the user's behavior information in the past n days, get the behavior information embedding and use it as the input of single-layer LSTM, then pass the output of the last cell through the full connection layer to get the prediction result 1; In the second part, we first use CNN (single layer convolution + maximum pooling) to extract the features of the user's behavior information for n days, and then use LSTM (similar to the above) to get the prediction result 2. Then we use the weighted operation to get the final prediction result

The loss function part adopts BCE and MSC models, which are determined according to specific evaluation indicators

## Run

python main.py

## References

* LSCNN: https://github.com/chantcalf/2018-Rank4-  choose NN1 model
* RNN: https://github.com/drop-out/RNN-Active-User-Forecast
