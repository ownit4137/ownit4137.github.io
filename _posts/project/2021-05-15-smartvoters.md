---
layout: post
title: 선거 정보 제공 웹 서비스
categories: [Project]
hide_last_modified: true
---

# 선거 정보 제공 웹 서비스

## 구조

1. 데이터베이스

- 공공데이터포털 API를 사용해 모든 데이터를 가져옴
- python을 이용하여 전처리 후 서버 데이터베이스에 저장

~~~py
# request voting place data(xml) and transform it into a dataframe

def get_mainpoll_df(sgId, sdName):
  base_url = ~url~

  queryParams = '?' + ~params~

  API_poll_url = poll_base_url + unquote(queryParams)

  response = urlopen(API_poll_url)
  json_str = response.read().decode('utf-8')

  json_object = json.loads(json_str)

  body = [json_object['getPolplcOtlnmapTrnsportInfoInqire']['item']]

  poll_data = pd.json_normalize(json_object['getPolplcOtlnmapTrnsportInfoInqire']['item'])
  return poll_data
~~~

2. 서버

- 배포를 위해 GCP[^1] 사용(무료 크레딧)
- DBMS로 MySQL 사용
- NodeJS를 사용해 API 구현

~~~js
app.get("/PollPlace", function (req, res) {
    var sql = 'SELECT DISTINCT sgId FROM election_code;'

    conn.query(sql, function (err, result) {
      if (err) {
        console.log(err);
      }else{
        var resultArray = Object.values(JSON.parse(JSON.stringify(result)));

        res.render("PollPlace.html", { codes: resultArray });
      }
    })
  });
~~~

[^1]: Google Cloud Platform

3. 클라이언트

- HTML, CSS, JS

## source

- [github]{:.heading.flip-title}

[github]: https://github.com/ownit4137/smartvoters
