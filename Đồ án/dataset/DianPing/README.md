# Dianping Review Dataset

Original link: http://yongfeng.me/dataset/

| Dataset           | \#User    | \#Item    | \#Inteaction | Sparsity | Interaction Type           | TimeStamp | User Context | Item Context | Interaction Context |
|-------------------|-----------|-----------|--------------|----------|----------------------------|-----------|--------------|--------------|---------------------|
| DianPing                                     | 542,706    | 243,247 | 4,422,473   | 99\.9967% | Rating<br/> \[0,5\] | √ | | √ | √ |

This dataset contains the user reviews as well as the  detailed business meta data information crawled from a famous Chinese online review webset [DianPing.com](http://www.dianping.com/), including the 3,605,300 reviews of 510,071 users towards 209,132 businesses. The numerical ratings of this dataset are used for collaborative filtering (Localized Matrix Factorization) in [1] and [2], and the textual reviews are used for sentiment analysis and explanable recommendation in [3] and [4], respectively. Detailed data format descriptions are included in the readme.txt file. This dataset can be downloaded here [download](http://pan.baidu.com/s/1dDxkY0x). The download password is "t23c", and the extraction password for the zip file is "yongfeng.me".

### References:

1. Yongfeng Zhang, Min Zhang, Yiqun Liu, Shaoping Ma and Shi Feng. Localized Matrix Factorization for Recommendation based on Matrix Block Diagonal Forms. In Proceedings of the 22nd International Conference on World Wide Web (WWW 2013), May 13 – 17, 2013, Rio de Janeiro, Brazil. [PDF](http://yongfeng.me/attach/lmf-zhang.pdf)
2. Yongfeng Zhang, Min Zhang, Yiqun Liu and Shaoping Ma. Improve Collaborative Filtering Through Bordered Block Diagonal Form Matrices. In Proceedings of the 36th Annual International ACM SIGIR Conference on Research and Development on Information Retrieval (SIGIR 2013), July 28 - August 1, 2013, Dublin, Ireland. [PDF](http://yongfeng.me/attach/abbdf-zhang.pdf)
3. Yongfeng Zhang, Haochen Zhang, Min Zhang, Yiqun Liu and Shaoping Ma. Do Users Rate or Review? Boost Phrase-level Sentiment Labeling with Review-level Sentiment Classification. In Proceedings of the 37th Annual International ACM SIGIR Conference on Research and Development on Information Retrieval (SIGIR 2014), July 6 - 11, 2014, Gold Coast, Australia. [PDF](http://yongfeng.me/attach/bps-zhang.pdf)
4. Yongfeng Zhang, Guokun Lai, Min Zhang, Yi Zhang, Yiqun Liu and Shaoping Ma. Explicit Factor Models for Explainable Recommendation based on Phrase-level Sentiment Analysis. In Proceedings of the 37th Annual International ACM SIGIR Conference on Research and Development on Information Retrieval (SIGIR 2014), July 6 - 11, 2014, Gold Coast, Australia. [PDF](http://yongfeng.me/attach/efm-zhang.pdf)

The dataset can be freely used for academic purpose, we appriciate if one (or more) of the following papers be cited in your publications that benifit from the dataset:

1. Yongfeng Zhang, Guokun Lai, Min Zhang, Yi Zhang, Yiqun Liu and Shaoping Ma. Explicit Factor Models for Explainable Recommendation based on Phrase-level Sentiment Analysis. In Proceedings of the 37th Annual International ACM SIGIR Conference on Research and Development on Information Retrieval (SIGIR 2014), July 6 - 11, 2014, Gold Coast, Australia.
2. Yongfeng Zhang, Min Zhang, Yiqun Liu, Shaoping Ma and Shi Feng. Localized Matrix Factorization for Recommendation based on Matrix Block Diagonal Forms. In Proceedings of the 22nd International Conference on World Wide Web (WWW 2013), May 13 - 17, 2013, Rio de Janeiro, Brazil. 
3. Yongfeng Zhang, Haochen Zhang, Min Zhang, Yiqun Liu and Shaoping Ma. Do Users Rate or Review? Boost Phrase-level Sentiment Labeling with Review-level Sentiment Classification. In Proceedings of the 37th Annual International ACM SIGIR Conference on Research and Development on Information Retrieval (SIGIR 2014), July 6 - 11, 2014, Gold Coast, Australia.
4. Yongfeng Zhang, Min Zhang, Yiqun Liu and Shaoping Ma. Improve Collaborative Filtering Through Bordered Block Diagonal Form Matrices. In Proceedings of the 36th Annual International ACM SIGIR Conference on Research and Development on Information Retrieval (SIGIR 2013), July 28 - August 1, 2013, Dublin, Ireland. [PDF]
   For any other issues or problems please contact us at zhangyf07@gmail.com

### reviews.txt

the reviews from Dianping.com, formated as 'key ^ json_line'
the key is the URL of the business, and the json_line is the content of a review, e.g.,

```json
http://www.dianping.com/shop/1567471 ^ {"srcType":0,"userId":242124,"rate":-1,"time":1250584020000,"restId":1567471,"flavor":2,"environment":2,"service":1,"cost":0,"stage":-1,"waiting":-1,"content":"\n","dishes":[],"atmosphere":[],"special":[]}
```

where the meaning of the keys in the json line are as follows:

```json
userId:	the user's id of the review, -1 for unknown
restId:	the business's id of the review, -1 for unknown
time:	Linux time stamp of the review, -1 for unknown
rate:	overall rating rated by the user, -1 for unknown
flavor:	rating on flavor given by the user, -1 for unknown
service:	rating on service rating given by the user, -1 for unknown
environmemnt:	rating on environmemnt of the business given by the user, -1 for unknown
cost:	average cost given by the user, 0 if the cost is not provided
stage:	stage in a day the dining was conducted. -1 for unknown, 1 for breakfast, 2 for lunch, 3 for dinner
wating: wating time, -1 for unknown
content:	review content
dishes:	the recommended dishes by the user
atmosphere:	restaurant atmosphere by the user
special:	special service provided to the user
```

### businesses.txt

​	the business meta data, also of the form `key ^ json_line`
​	the key is the URL of the business, and the json_line is the metadata of the business, e.g., `http://www.dianping.com/shop/1589707`
the meaning of the keys in the json_line are as follows:

```json
ID = 0;	//business id
NAME = 1;	//business name
CITY = 2;	//the city where the business is located, please refer to the city.txt file for the name of the city codes
SCORE = 3;	//the overall rating of the bussiness, this rating is calculated by Dianping.com itself according to the user reviews, and the rating is displayed in the business front page
FLAVOR = 4;	//the flavor rating of the business, also calculated by Dianping and displayed on the front page
ENVIRONMENT = 5;	//the environment rating of the business, as above
SERVICE = 6;	//the service rating of the business, as above
ADDRESS = 7;	//the address of the business
TEL = 8;	//telephone number of the business
SHARE = 9;	//the number of the website users that clicked 'share to my friends' button for the business
DESC = 10;	//a short text discription of the business, written by the business owner usually
DISH = 11;	//recommeded dishes of the business, each recommended dish is accompanied by the number of recommendations
ATMOSPHERE = 12;	//atmosphere of the business (resuaurant)
SPECIAL = 13;	//special service of the business
SHOPHOUR = 14;	//opening hour of the business
WAY = 15;	//(public) traffic route of the business
LAT = 16;	//latitude of the location of the business
LNG = 17;	//longitude of the location of the business
STYLE = 18;	//business style
COST = 19;	//average cost of the business
TAGS = 20;	//user generated tags of the business
AREAS = 21;	//business area in the city of the business
PAGE = 30;	//the website page source code of the business
```

### city.txt

​	the numerical codes of each city