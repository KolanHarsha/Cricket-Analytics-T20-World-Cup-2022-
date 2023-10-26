# Cricket-Analytics-T20-World-Cup-2022-
The main goal of this repository is to create a powerful dashboard in Power BI for identifying and visualizing the top performers of ICC T-20 Worlcup held in 2022.
The process can be divided into the following steps:
- Web-Scraping
- Data pre-processing and transformation using python
- Data Modelling
- Defining Key-measures
- Analysing the stats using dashboard 

## **Tools**
<img src="https://github.com/KolanHarsha/Cricket-Analytics-T20-World-Cup-2022-/assets/110462466/0365cee4-ab29-40c4-ba74-979a89e5eda6" alt="jup" width="150" height="150">
<img src="https://github.com/KolanHarsha/DDos-detection-Using-Machine-Learning/assets/110462466/88e29b73-06a2-48ac-8e80-0cd755dd980e" alt="jup" width="150" height="100">
<img src="https://github.com/KolanHarsha/DDos-detection-Using-Machine-Learning/assets/110462466/ec05c02a-389a-4363-8b8c-9b1ba8ca28b0" alt="python" width="150" height="100">
<img src="https://github.com/KolanHarsha/Cricket-Analytics-T20-World-Cup-2022-/assets/110462466/befd90d2-30d4-457c-b12d-e785b2610abd" alt="power" width="150" height="100">

## **Web-Scraping**
1. Go to the Web-Scraper IDE on [Bright Data](https://brightdata.com/) platform and run the 4-javascripts files individually which are provided in the web_scraping_codes directory.
2. The Bright Data automatically performs the web-scraping on the official [ESPN](https://www.espncricinfo.com/records/tournament/team-match-results/icc-men-s-t20-world-cup-2022-23-14450) website to retrieve match-results, batting-summary, bowling-summary, players-info of the ICC T-20 World Cup 2022 using proxy networks. Once the web-scraping is done the json files are sent to your email.
3. The json files which I received are provided in the t20_json_files directory.

## **Data pre-processing and transformation using python**
1. Once the 4-json files are received the next step is to parse them and convert them into a csv file. Launch the jupyter notebook in your local machine and run the Cricket-data-preprocessing.ipynb file which is provided in the Data-preprocessing directory.
2. The dim_match csv file which is generated after parsing match_results.json file has a match_id column which is like a primary key. I used this primary key to establish a link between match-results, batting summary and bowling summary. This can be done by creating a dictionary with keys as "team1" vs "team2" and "match_id" as its values which is then mapped with batting_summary, bowling_summary DataFrames.
<img width="535" alt="Screenshot 2023-10-25 190216" src="https://github.com/KolanHarsha/Cricket-Analytics-T20-World-Cup-2022-/assets/110462466/805d6ed8-9720-46a7-8f21-89c6721ba1d1">

3. The match_id column now acts a foreign key in fact_batting and fact_bowling files. 
4. The final csv files are provided in the csv.files directory.

## **Data Modelling**
1. Once the data is available in csv files it is then loaded onto the Power BI for visualization. It is important to create a link between the four files which is known as data-modelling before going to visualization.
2. The data modelling process is shown below. The match_id column is used to link "fact_batting_summary", "fact_bowling_summary" with  "dim_match_summary" and  name column is used to link "fact_batting_summary", "fact_bowling_summary" with "dim_players".


<img width="818" alt="image" src="https://github.com/KolanHarsha/Cricket-Analytics-T20-World-Cup-2022-/assets/110462466/730a9584-b06a-4067-8c18-5bd87e57b1c3">

## **Defining Key-measures**

1. The key measures and calculated columns which are created  are provided in the key_measures excel file.
2. The final file after creating the dashboard is provided in the Dashboard directory.

## **Analysing the stats using dashboard**
1. The top power-hitter players with strike-rate> 140, boundary%> 50%, batting position< 4 are shown below.

   <img width="835" alt="image" src="https://github.com/KolanHarsha/Cricket-Analytics-T20-World-Cup-2022-/assets/110462466/5f697273-9584-498c-b9fa-c865691cbe6c">


2. The top middle order batters with strike-rate> 120, batting position >=3, batting average >40 are shown below.

   <img width="835" alt="image" src="https://github.com/KolanHarsha/Cricket-Analytics-T20-World-Cup-2022-/assets/110462466/fd2c6bb3-2bda-47c5-b5e2-33c11c1da9ce">


3. The top finishers with batting.Avg> 25, strike-rate> 130, runs> 100, with wickets>1 are shown below.

   <img width="835" alt="image" src="https://github.com/KolanHarsha/Cricket-Analytics-T20-World-Cup-2022-/assets/110462466/5a8d943e-7ae6-4dd2-8fb9-84bf9dc08cba">


4. The top All-rounders with strike-rate> 165, batting.Avg> 20, economy< 6.5, bowling strike-rate< 20 are shown below.

   <img width="835" alt="image" src="https://github.com/KolanHarsha/Cricket-Analytics-T20-World-Cup-2022-/assets/110462466/7aaf4a17-f9d6-4b82-9e4d-06c0353e0905">


5. The top fast bowlers with No of balls bowled> 100, wickets>5, bowling strike-rate< 15, Dot Ball%> 45% are shown below.

   <img width="835" alt="image" src="https://github.com/KolanHarsha/Cricket-Analytics-T20-World-Cup-2022-/assets/110462466/15e9f4c2-8254-4a34-8942-c4d1303799c3">


## **Contributors**
- Sai Harsha Vardhan Reddy, Kolan- skolan@horizon.csueastbay.edu, harsha62334@gmail.com

Thanks for reading!
   
