## 장고 Model과 ORM에 대해 알아봅시다.
#### 장고 Model
- 데이터베이스의 테이블 구조를 정의하는 클래스
  - 데이터의 구조, 속성 및 관계를 정의
  - 데이터가 데이터베이스에 어떻게 저장될지를 결정
- `django.db.models.Model`을 상속받아 정의
#### 장고 ORM(Object-Relational Mapping)
- 파이썬 객체를 사용해 데이터베이스 조작을 가능하게 하는 기술
  - SQL을 직접 사용하지 않고 파이썬 문법으로 데이터베이스를 쉽게 관리

## 장고 Model로 테이블을 만드는 방법을 정리해봅시다.
#### 1. 모델 클래스 정의하기
- models.py 파일에 클래스로 정의
#### 2. 모델을 마이그레이션 파일로 변환하기
- 정의한 후에는 이 모델을 데이터베이스에 반영하기 위해 마이그레이션 파일을 생성
- `python manage.py makemigrations`
#### 3. 마이그레이션을 데이터베이스에 적용하기
- `python manage.py migrate`

## 장고 ORM 메서드들의 기능을 정리해봅시다.
#### Class.objects.get()
- 특정 조건에 일치하는 단일 객체를 조회
- 사용법 : `ModelClass.objects.get(조건)`
- 반환값 : `조건에 맞는 단일 객체`
- 오류
  - 조건에 맞는 객체가 없을 경우: `DoesNotExist`
  - 조건에 맞는 객체가 여러 개일 경우: `MultipleObjectsReturned`
#### Class.objects.all()
- 해당 모델의 모든 객체를 조회
- 사용법 : `ModelClass.objects.all()`
- 반환값 : `쿼리셋(QuerySet)`
#### Class.objects.filter()
- 특정 조건을 만족하는 객체들을 조회
- 사용법 : `ModelClass.objects.filter(조건)`
- 반환값 : `쿼리셋(QuerySet)`

## 자주 쓰이는 HTML 태그에 대해 정리해봅시다.
#### `<h1>` ~ `<h6>`
- 제목을 정의하는 태그
- `<h1>`은 가장 중요한 제목, `<h6>`은 가장 덜 중요한 제목
#### <p>
- 단락을 정의하는 태그
- 텍스트를 문단 단위로 구분
#### <a>
- 하이퍼링크를 만드는 태그
- `href` 속성을 통해 링크할 URL을 지정
- `<a href="https://www.example.com">Visit Example</a>`
#### <li>
- 목록 항목을 정의하는 태그
- `<ul>` 또는 `<ol>` 안에서 사용
  - <ul>
    - 순서 없는 목록을 정의하는 태그
  - <ol>
    - 순서 있는 목록을 정의하는 태그
#### <form>
- 사용자 입력을 제출할 수 있는 폼을 정의하는 태그
- `action` 속성으로 데이터를 보낼 URL을 지정, `method` 속성으로 전송 방식을 설정
#### <input>
- 다양한 종류의 입력 필드를 정의하는 태그
- `type` 속성에 따라 텍스트, 비밀번호, 라디오, 체크박스 등 다양한 입력 타입을 지정
#### <div>
- 블록 요소
- 콘텐츠를 그룹화할 때 사용

## 장고 Template 문법에 대해 알아봅시다.
- HTML 파일 내에서 파이썬 코드와 데이터를 표시하는 기능을 제공하여 동적인 웹 페이지를 만들 수 있게 해줌
#### 변수 출력
- 중괄호 두 개 `{{ }}`
  - 템플릿에서 전달받은 데이터를 출력
#### 태그
- 템플릿 언어의 논리적 구조를 제어하기 위해 사용
- `{% %}`
