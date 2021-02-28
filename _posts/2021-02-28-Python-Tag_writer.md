---
title: "Python 1)Tag Writer"
last_modified_at: 2019-12-25T19:28:00-05:00
categories:
  - 답답해서 해본 코딩
tags:
  - Python
---

Input
=====

19년 12월? 개발을 1도 모르는 상황에서, 기획을 한 아이디어를 표현하고 싶은데,   
기획 문서로 표현하는 것에 한계가 있다는 생각이 들었습니다.    

**`넷플릭스` 같은 추천 시스템을 기획하는 것**

그러다 뭐라도 배워야 표현할 수 있을 것다는 생각에 `edwith`에서 **PY4E**를 들었습니다.   
3주 정도 주말에 배워서, 파이썬 기초와 자료형에 대해 배웠고, 딕셔너리 구조를 이용해서   
지금보면 (지금도 실력이라 할 것 없지만...) 왜 이렇게 했을까하는 툴을 3가지 만들었습니다.   

아, 그때는 Tkinter도 몰라 도스로 변환해서 exe를 만들었습니다.   

**`목표` 테그 입력하는 툴 만들기**


Process
=====

```python
#Tag Writer v0.2 Jeremy Lee
Book_Title = input ("도서명 : ")
#Book_Title_db = list()
Book_Title_db = dict()
Book_Title_dic = dict()

while True :
    tag_categories = input ("카테고리 : ")
    if tag_categories == "저장" :
        #Book_Title_db.append(Book_Title_dic)
        Book_Title_db[Book_Title]=Book_Title_dic
        print(Book_Title_db)
        break
    tag_categories_dic = dict()
    while True :
        tag_keys = input ("구분값 : ")
        if tag_keys == "저장" :
            Book_Title_dic[tag_categories] = tag_categories_dic
            print(Book_Title_dic)
            break
        tag_values = input ("+/- : ")
        # tag_values는 y와 n으로 표시
        tag_categories_dic[tag_keys] = tag_values
        print("입력되었습니다:\n",tag_categories_dic)

print (Book_Title_db)

save_file = input("저장할 파일명을 입력하세요 :")
with open(str(save_file)+".txt",'w') as file :
    file.write(str(Book_Title_db))
```


Output
=====

다른 연구 업무를 하게 되어 기획 자체가 의미없어졌지만,   
그래도 뭐가 목표를 가지고 만든 첫 코딩(?)작입니다.