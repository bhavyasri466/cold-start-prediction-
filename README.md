# cold-start-prediction-
https://colab.research.google.com/drive/1Am4rITl2HKeHF-zl-We0aRIv2eKVS1Tp


“Serverless Cold-Start Latency Prediction Using Deep Learning”

The main focus of the PPT must be CNN-LSTM, because my professor specifically asked me to use this model. The other models should be included only for comparison.

Please cover the following topics:

1. Objective of the Paper

- Predict serverless cold-start latency using historical execution data.
- Study how deep learning models can learn patterns from previous latency observations.
- Develop and evaluate a CNN-LSTM-based prediction model.

2. Classification or Regression

- This is a regression problem because the objective is to predict a continuous numerical latency value.
- It is not a classification problem.
- The adaptive ensemble uses an internal classification model to select the best prediction model, but the main project task is regression.

3. Dataset Used

- Dataset: Alibaba FaaSNet serverless trace dataset.
- Original records: 1,629,445.
- After removing two negative-latency records: 1,629,443.
- Features include function name, latency, runtime, memory, region and timestamp.
- Feature engineering includes previous latency values (lag features), historical mean and standard deviation, execution history count, time gaps and time-based features.
- Explain how the dataset was cleaned, processed and divided chronologically into training, validation and testing sets.

4. Main Architecture – CNN-LSTM
This should be the most detailed section of the PPT.

Explain:

- What CNN is and how it extracts local patterns from sequential latency data.
- What LSTM is and how it learns temporal dependencies from historical observations.
- Why combining CNN and LSTM is useful for latency prediction.
- The architecture and flow of data through the model.
- How the model receives historical latency and contextual features and predicts the next latency value.

Include a clear CNN-LSTM architecture diagram.

5. Why CNN-LSTM Was Used

- CNN can identify local patterns and relationships in historical observations.
- LSTM can learn longer-term sequential dependencies.
- Combining both allows the model to learn local and temporal patterns.
- It is suitable for exploring time-dependent patterns in serverless latency data.

6. Experimental Methodology
Explain the complete experiment:

- Dataset collection and preprocessing.
- Feature engineering.
- Chronological train-validation-test split.
- Feature scaling and sequence preparation.
- CNN-LSTM model construction.
- Model training and validation.
- Prediction on the test dataset.
- Evaluation using MAE, RMSE and R².

7. CNN-LSTM Training Configuration
Include:

- Optimizer: RMSprop.
- Learning rate: 0.001.
- Loss function: Huber loss.
- Batch size: 1024.
- Maximum epochs: 10.
- Early stopping and learning-rate reduction were used to control training.

8. Results of CNN-LSTM

Our CNN-LSTM results:

- MAE: 935.8665
- RMSE: 2485.0254
- R²: 0.8750

Explain what each evaluation metric means and how to interpret these results.

9. Comparison With Other Models

Include a comparison table:

Model| MAE| RMSE| R²
Persistence Baseline| 764.3710| 2385.6570| 0.8848
ABiGRU| 2353.4758| 5821.9911| 0.3141
CNN-LSTM| 935.8665| 2485.0254| 0.8750
XGBoost| 833.3454| 2189.8872| 0.9030
Residual Hybrid| 759.7931| 2323.9110| 0.8907
Adaptive Ensemble| 725.9829| 2201.0392| 0.9020

CNN-LSTM must receive the most explanation and attention. Clearly mention that other models were implemented as comparative approaches. Do not claim CNN-LSTM achieved the best overall result.

10. What We Have Done

- Processed a large Alibaba FaaSNet dataset.
- Performed feature engineering using historical latency and execution information.
- Implemented CNN-LSTM as the primary deep learning model.
- Implemented additional models for comparison.
- Trained and evaluated the models.
- Compared their prediction performance using standard regression metrics.

11. Future Improvements
Discuss possible improvements:

- Adding more CNN convolutional layers.
- Using stacked LSTM layers.
- Experimenting with Bidirectional LSTM.
- Adding an attention mechanism.
- Trying CNN-BiLSTM or CNN-LSTM-Attention.
- Hyperparameter optimization.
- Evaluating on larger datasets covering multiple days and different workloads.

12. Conclusion
Summarize how CNN-LSTM can learn temporal and local patterns from historical serverless execution data and can be applied to cold-start latency prediction. Mention the experimental findings and possible improvements.

PPT requirements:

- Around 12–15 slides.
- Professional academic/research presentation style.
- Use architecture diagrams and workflow diagrams.
- Include result tables and suitable graphs.
- Keep explanations understandable and technically accurate.
- Give CNN-LSTM the highest priority throughout the presentation.
- Avoid overcrowding slides with paragraphs.
- Include a final references slide.
