# Selenium 

### :heavy_check_mark: Selenium VS BeautifulSoup 비교

####  Selenium

웹 브라우저를 자동으로 제어할 수 있게 함

#### BeautifulSoup

html과 xml 문서를 parsing하기 위한 패키지. html에서 데이터를 ㅜ추출하는 데 유용한 구문 분석 트리를 생성함.



## element 찾기

### 1. method로 element 선택

1개

```
find_element_by_id
find_element_by_name
find_element_by_xpath
find_element_by_link_text
find_element_by_partial_link_text
find_element_by_tag_name
find_element_by_class_name
find_element_by_css_selector
```

여러개

```
find_elements_by_name
find_elements_by_xpath
find_elements_by_link_text
find_elements_by_partial_link_text
find_elements_by_tag_name
find_elements_by_class_name
find_elements_by_css_selector
```



- driver.find_elements_by_tag_name

  ```
  # body = driver.find_element_by_tag_name('body')
  ```

- driver.find_element_by_id

  ```
  # driver.find_element_by_id('search').click()
  ```

- driver.find_element_by_link_text

  ```
  driver.find_element_by_link_text('필터').click()
  ```

  

- driver.find_element_by_**css_selector**

  ```
  driver.find_element_by_css_selector('#product_contents_review > div > div > ul > li:nth-child(2) > button').click()  #이 상품의 리뷰 탭 클릭
  ```

- driver.find_element_by_**xpath**

  ```
  element = driver.find_element_by_xpath('//*[@id="navigation-container"]/div/nav/div[1]/div/div/div/form/input')
  
  ```



### 2. find_element By로 정리하기

각 element에 따라 method를 따로 사용하는 것 보다 깔끔하게 정리하기 위해 By를 사용해 봅시다.

- `driver.find_element(By.<속성>, '<속성 값>')`
- 여러 element를 찾을 경우 find_elements

```python
from selenium.webdriver.common.by import By

driver.find_element(By.XPATH, '//button[text()="Some text"]')
driver.find_element(By.XPATH, '//button')
driver.find_element(By.ID, 'loginForm')
driver.find_element(By.LINK_TEXT, 'Continue')
driver.find_element(By.PARTIAL_LINK_TEXT, 'Conti')
driver.find_element(By.NAME, 'username')
driver.find_element(By.TAG_NAME, 'h1')
driver.find_element(By.CLASS_NAME, 'content')
driver.find_element(By.CSS_SELECTOR, 'p.content')

driver.find_elements(By.ID, 'loginForm')
driver.find_elements(By.CLASS_NAME, 'content')
```



### send_keys

- ```
  driver.find_element_by_id('search').send_keys(keyword) #키워드를 넣고
  driver.find_element_by_id('search').send_keys(Keys.ENTER) #enter키를 쳐라
  ```

- 스크롤 다운

  ```
  body = driver.find_element_by_tag_name('body')
  body.send_keys(Keys.PAGE_DOWN)
  ```

- 

- 

- driver.back() : 뒤로가기?!

### driver.close() vs driver.quit() 차이

- `driver.close()` => 탭 하나 종료
- `driver.quit()` => 모든 탭 종료