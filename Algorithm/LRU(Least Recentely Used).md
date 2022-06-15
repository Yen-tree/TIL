# LRU 알고리즘 (Least Recentely Used)

## LRU란?

- Cache 알고리즘 중 하나

- Least Recentely Used -> 최소 최근 사용
- 가장 오랫동안 참조되지 않은 페이지를 교체하는 방식
- 가장 오랫동안 참조되지 않은 페이지는 앞으로도 참조될 확률이 낮다는 가설 하에 쓰이는 알고리즘



## LRU의 원리

- 가장 오랫동안 참조되지 않은 페이지를 없애면 된다.

- 참조가 되면(Cache Hit) 순서를 최근으로 옮긴다.



## LRU의 개념

- head: 가장 최근
- tail: 가장 오래된

- Cache Hit: CPU가 참조하고자 하는 메모리가 캐시에 존재할 경우
- Cache Miss : CPU 가 참조하고자 하는 메모리가 캐시에 존재하지 않을 경우