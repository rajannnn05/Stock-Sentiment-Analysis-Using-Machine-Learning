# Stock-Sentiment-Analysis-Using-Machine-Learning
*Overview*:
This project applies machine learning and natural language processing techniques to analyze the sentiment of financial news headlines and predict stock price movements. By assessing the sentiments expressed in news articles and correlating them with stock price data, the project aims to provide actionable insights for investors and financial analysts, supporting better trading decisions and risk management.

*Significance*:
Understanding market sentiment is vital for investors, traders, and analysts, as positive or negative sentiment can drive significant stock price changes. This project leverages sentiment analysis to:

Improve trading strategies by incorporating sentiment trends.

Mitigate risks by detecting negative sentiment early, enabling timely portfolio adjustments.

*Methodology*:
1. Data Collection

News headlines were scraped from seekingalpha.com and stored in news.csv with corresponding dates.

Historical stock price data was fetched using the yfinance Python library.

2. Data Cleaning and Preprocessing

Headlines from the same date were merged.

Text preprocessing included converting to lowercase, removing punctuation, and lemmatization to normalize words to their base forms.

3. Sentiment Analysis

Used TextBlob to compute subjectivity and polarity scores for each headline:

Polarity: Ranges from -1 (negative) to 1 (positive).

Subjectivity: Ranges from 0 (objective) to 1 (subjective).

Applied NLTK’s VADER SentimentIntensityAnalyzer to obtain positive, neutral, negative, and compound sentiment scores.

4. Feature Extraction

Employed TF-IDF (Term Frequency-Inverse Document Frequency) to convert text data into numerical features.

Applied Latent Dirichlet Allocation (LDA) for topic modeling to uncover hidden thematic structures in the headlines.

5. Data Labeling

Labeled each data point based on the stock’s movement the day after news publication: 1 for upward movement, 0 for downward.

6. Model Development

Trained a Linear Discriminant Analysis (LDA) classifier—a robust machine learning algorithm for distinguishing between classes—using the extracted features and labeled data.

7. Training and Testing

Split the dataset into training and testing sets (80/20 split).

Trained the model and evaluated its predictive performance.

8. Model Evaluation

Evaluated using metrics such as accuracy, precision, recall, F1 score, confusion matrix, and ROC curve analysis.

*Trading Strategy*:
Implemented a simple buy-and-hold strategy based on model predictions and risk management rules.

Initial capital: $10,000.

Buy when the model predicts an upward movement, sell on downward prediction or when stop-loss/take-profit thresholds are met.

Stop-loss set at 5%, take-profit at 10%.

Portfolio value is tracked over time, and performance is visualized with buy/sell signals on price charts.

*Performance Metrics*:
Final Portfolio Value: $2,956,278.63 (from $10,000 initial capital)

Total Return: 294.63%

Sharpe Ratio: 7.84 (risk-adjusted return)

Maximum Drawdown: -6.21%

Number of Trades Executed: 495

Win Ratio: 49.47%

*Drawbacks*:
Sentiment analysis accuracy can be affected by ambiguous language, sarcasm, and context-dependent meanings.

Data quality and availability may vary, requiring careful selection and preprocessing.

Model performance may fluctuate with market conditions and external events, necessitating regular updates and recalibration.
