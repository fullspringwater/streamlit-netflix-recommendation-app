<h1 align="center"> π streamlit-netflix-recommendation-app</h1>

## π Description

β λ·νλ¦­μ€ μμ μ λͺ©, μ₯λ₯΄, νμμ μ ν, κ²μνμ¬ κ·Έμ ν΄λΉνλ νλ‘κ·Έλ¨μ λν μ λ³΄λ₯Ό λ³Ό μ μμ΅λλ€.

β ν΄λΉ νλ‘κ·Έλ¨κ³Ό λΉμ·ν μμμ μΆμ²ν΄ λ³΄μ¬μ€λλ€. 

β μΆμ² μμ€νμ K-NN μκ³ λ¦¬μ¦μ μ΄μ©ν΄ κ°μ₯ μ μ¬ν 5κ°μ νμ΄νμ μΆμΆνμ΅λλ€.

## π Dataset Source

 π μΆμ² : https://www.kaggle.com/datasets/victorsoeiro/netflix-tv-shows-and-movies?select=titles.csv

 - **ID** :  νμ΄ν ID
 - **title** : μ λͺ©
 - **show type** : TV  λλ μν
 - **description** : κ°λ΅ν μ€λͺ
 - **release year** : μΆμ μ°λ
 - **age certification** : μ°λ Ή μΈμ¦
 - **runtime** : μνΌμλ(SHOW) λλ μνμ κΈΈμ΄
 - **genres** : μ₯λ₯΄ λͺ©λ‘μλλ€.
 - **production countries** : νμ΄νμ μ μν κ΅­κ° λͺ©λ‘
 - **seasons** : SHOWμΈ κ²½μ° μμ¦ μ
 - **IMDB ID** : IMDBμ νμ΄ν
 - **IMDB Score** :  IMDB μ μ.
 - **IMDB Votes** : IMDB ν¬νμ
 - **TMDB Popularity** :  TMDB μΈκΈ°λ
 - **TMDB Score** :  TMDB μ μ
##
## π  Environment

β Language : Python 3.7

##
## π¨ Installation

```
pip install streamlit
```

```
pip install youtube-search-python
```

```
pip install joblib
```

```
pip install plotly==5.8.0
```

```
pip install scikit-learn
```
## πΌ  VideosSearch

```python
from youtubesearchpython import VideosSearch
import streamlit as st
# Youtube λμμ κ²μν μμ μΆλ ₯
def videosSearch(search):
    videosSearch = VideosSearch('Netflix {}'.format(search), 
                                    limit = 3)
    j = 5
    for i in range(len(videosSearch.result()['result'])) :
        if search.lower() in videosSearch.result()['result'][i]['title'].lower() :
            j = i
            break                                
    if j != 5 :
        video_url = videosSearch.result()['result'][j]['link']
        st.video(video_url)
    else : 
        st.info('κ΄λ ¨ μμμ μ°Ύμ μ μμ΅λλ€.')
```
## πΌ Recommendation System

β KNNμ μ΄μ©ν΄ κ°μ₯ κ±°λ¦¬κ° κ°μ₯ κ°κΉμ΄ (μ μ¬λκ° κ°μ₯ λμ) 5κ°λ₯Ό λ½μ μΆμ²νλλ‘ νμ΅λλ€.
![knn](https://user-images.githubusercontent.com/105832330/172280125-12d3f63b-3eea-48b3-ae72-bc94da8070c4.png)





## πΏ Usage

### μ€ννκΈ°
![netflix_app_begin](https://user-images.githubusercontent.com/105832330/172292297-fabb8eb7-6486-4965-b65d-2dabba0c9783.gif)


### νμ€νΈ
![netflix_app_test](https://user-images.githubusercontent.com/105832330/172278582-f52e660b-2491-492b-a061-2fd570e59677.gif)

### Url
http://ec2-3-39-230-35.ap-northeast-2.compute.amazonaws.com:8503/
