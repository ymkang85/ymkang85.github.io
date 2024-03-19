---
sort: 1
---

# fastapi

1. q는 필수가 아님. 기본값은 None
-> q: Union[str, None] = None 

2. q는 필수가 아니고 최대 50자리 까지 가능. 기본값은 None
-> q: Union[str, None] = Query(default=None, max_length=50)

3. q는 필수가 아니고 최소3자리, 최대 50자리 까지 가능. 기본값은 None
-> q: Union[str, None] = Query(default=None, min_length=3, max_length=50)

4. q의 기본값은 fixedquery이고 최소 3자리
-> q: str = Query(default="fixedquery", min_length=3)

5. q의 값을 다중으로 설정(List 이용) -> fastapi에서 아이템 추가x
-> q: Union[List[str], None] = Query(default=None)

6. q의 값을 다중으로 설정(list 이용) -> fastapi에서 아이템 추가 가능
-> q: list = Query(default=[])

7. q의 기본값 추가(title, description)
-> q: Union[str, None] = Query(
        default=None,
        title="Query string",
        description="Query string for the items to search in the database that have a good match",
        min_length=3,
    )

8. 별칭 지정(파이썬의 유효하지 않은 변수명을 설정할 때 이용-alias)
-> q: Union[str, None] = Query(default=None, alias="item-query")

9. 매개변수 사용하지 않도록 설정
-> q: Union[str, None] = Query(
        ... 
        ... 
        ...
        deprecated=True
        ...
    )

참고 : https://fastapi.tiangolo.com/ko/tutorial/query-params-str-validations/
```
