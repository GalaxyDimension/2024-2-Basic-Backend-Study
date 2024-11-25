## FK에 대해 공부해봐요
- Foreign Key(FK) 외래키
- 테이블 간 1:N(일대다) 관계를 설정
- 데이터의 참조 무결성을 유지
- 참조 대상 테이블의 기본 키를 외래 키 필드가 가리킴
- 참조된 데이터가 삭제되거나 변경될 경우, 외래 키를 통해 관련 데이터도 영향을 받을 수 있음
### 일대일,일대다, 다대다 관계를 테이블로 구현하는 법에 대해 정리해봐요
### 일대다 관계를 장고를 이용해 테이블로 구현하는 법에 대해 공부해봐요
- 일대일(1:1) 관계
  ```python
  class Profile(models.Model):
    user = models.OneToOneField(User, on_delete=models.CASCADE)
    introduce = models.TextField()
  ```
  - OneToOneField
  - 한 레코드가 다른 테이블의 한 레코드와만 연결되도록 강제
- 일대다(1:N) 관계
  ```python
  class BlogPost(models.Model):
    title = models.CharField(max_length=200)
    content = models.TextField()
    author = models.ForeignKey(Author, on_delete=models.CASCADE)
  ```
  - ForeignKey
- 다대다(N:M) 관계
  ```python
  class BlogPost(models.Model):
    title = models.CharField(max_length=200)
    content = models.TextField()
    tags = models.ManyToManyField(Tag)
  ```
  - ManyToManyField
  - 다대다 관계를 자동으로 연결 테이블을 생성하여 관리
  - 중간 테이블을 자동 생성하므로 추가 설정이 필요하지 않음
