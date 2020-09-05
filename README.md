# Binary-Search

이진탐색 알고리즘

## 사용을 고려해볼 만 상황

+ 탐색범위가 1,000만 단위 이상을 넘어갈 때

## 제약 조건

+ 정렬이 되어있어야 한다는 점

## 이진 탐색 트리

+ 이진 탐색이 동작할 수 있도록 고안된, 효율적인 탐색이 가능한 트리


## 구현

```cpp

vector<int> datasets;

int binary_search(start, end, target){
    while(start <= end){
        int mid = (start + end) / 2;
        if(datasets[mid] == target){
            return mid;
        }else if(datasets[mid] < target){
            start = mid + 1;
        }else{
            end = mid - 1;
        }
    }
    return -1;
}
```

## STL 사용

```cpp
#include <algorithm>

template <class ForwardIterator, class T>
  bool binary_search (ForwardIterator first, ForwardIterator last, const T& val)
{
  first = std::lower_bound(first,last,val);
  return (first!=last && !(val<*first));
}
```

boolean 형태로 return 된다. 적절히 활용할 것