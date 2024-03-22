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
            answer = 0 # 답을 리턴할 변수를 선언한다
            arr = [] # 빈 배열을 선언한다.
            if left>right : # 만일 왼쪽의 수가 더 클 경우
                left,right=right,left # 두 수의 순서를 바꿔준다.
            while left < right+1: #그 후 가장 큰 수까지 while문을 활용하여 조건에 맞게 합을 구한다.
                for i in range(1, left+1): # 과정 1에서 찾았던 약수 구하는 공식
                    if left%i == 0:  # 과정 1에서 찾았던 약수 구하는 공식
                        arr.append(i)  # 과정 1에서 찾았던 약수 구하는 공식
                    
                if len(arr)%2==0: # 약수가 저장된 배열의 길이를 2로 나눈 값의 나머지가 0일 경우
                    answer+=left # 문제에서 지시한대로 합쳐준다. 
                else:
                    answer-=left # 그렇지 않을 경우에는 빼준다.
                arr=[] # 중요! 빈배열로 꼭 만들어줘야 한다. 그러지 않을 경우 상단의 for문에서 값이 들어있는 배열을 활용하게 된다.  
                left+=1  # while문을 빠져나가기 위해선 꼭 이 구문이 필요하다.
        return answer # 합계를 리턴해준다.
''' 
```

