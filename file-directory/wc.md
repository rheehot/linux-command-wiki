# wc

파일 안의 `행`, `단어`, `문자`, `바이트`를 계산하는 명령어  

## 사용법

``` shell
wc [-lwcm] [file...]
```

| 옵션 	| 설명 	|
|:----:	|:------------------------- |
| -l 	| 파일의 행(라인) 수를 계산 |
| -w 	| 파일의 단어 수를 계산 |
| -c 	| 파일의 바이트 수를 계산 |
| -m 	| 파일의 문자 수를 계산. 만약, locale이 멀티바이트 문자를 지원하지 않으면 -c 옵션과 동일하게 동작 |

wc의 표준 입력으로 파일을 입력해 출력하거나 파이프 라인을 통해 명령어를 사용할 수 있음

``` shell
# 일반적인 사용
❯ wc -wl test.txt

# 파이프문자(|)랑 같이 사용
❯ cat test.txt | wc -wl
```

### 옵션 사용

'test.txt' 파일은 아래와 같이 내용이 작성되었고, 해당 파일로 옵션 설명

``` shell
❯ cat test.txt
123 456 789
abc def ghi
가 나 다 라
```

#### 옵션을 사용하지 않았을 때

옵션을 사용하지 않으면 행, 단어, 바이트 순으로 출력

``` shell
❯ wc test.txt
#      행(-l)  단어(-w) 바이트(-c)
       3       10       40 test.txt
```

#### 행(라인) 수 출력

`-l` 옵션을 사용하면 행(라인) 수를 출력할 수 있음

``` shell
❯ wc -l test.txt
       3 test.txt
```

#### 단어 수 출력

`-w` 옵션을 사용하면 구분자로 **공백문자**를 사용해 단어 수를 출력할 수 있음

``` shell
❯ wc -w test.txt
      10 test.txt
```

#### 바이트 수 출력

`-c` 옵션을 사용하면 바이트 수를 출력할 수 있음

``` shell
❯ wc -c test.txt
      40 test.txt
```

#### 여러 개의 옵션 사용

옵션의 위치와 상관없이 항상 동일한 순서(행, 단어, 바이트)로 출력

```
❯ wc -wl test.txt
#      행(-l)  단어(-w)
       3       10       test.txt
```
