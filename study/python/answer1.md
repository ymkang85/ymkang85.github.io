# python


# 프로그래머스 문제 풀이

문제: 
```yml
-> 두 정수 left와 right가 매개변수로 주어집니다. left부터 right까지의 모든 수들 중에서 
   약수의 개수가 짝수인 수는 더하고, 약수의 개수가 홀수인 수는 뺀 수를 return 하도록 
   solution 함수를 완성해주세요.
```

풀이과정 :

1. 약수를 구하는 함수를 먼저 구함. [참고](https://minnit-develop.tistory.com/16)
```yml
-> 
'''
  def getMyDivisor(n):
    divisorsList = []
    for i in range(1, n + 1):
        if (n % i == 0) :
            divisorsList.append(i)
    return divisorsList
'''
```
2. while문을 활용한 함수 작성
```yml
->  
'''
      def solution(left, right):
            answer = 0 
            arr = []
            if left>right : 
                left,right=right,left
            while left < right+1:
                for i in range(1, left+1): 
                    if left%i == 0: 
                        arr.append(i) 
                    
                if len(arr)%2==0: 
                    answer+=left  
                else:
                    answer-=left 
                arr=[] # 중요! 빈배열로 꼭 만들어줘야 한다. 그러지 않을 경우 상단의 for문에서 값이 들어있는 배열을 활용하게 된다.  
                left+=1 
''' 
```

