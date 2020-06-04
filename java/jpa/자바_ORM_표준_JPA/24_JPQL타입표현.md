- 문자: 'HELLO', 'Sh''s'
- 숫자 : 10L(Long), 10D(Double), 10F(Float)
- Boolean : TRUE,FALSE
- ENUM : jpabook.MemberType.Admin (패키지명 포함)
- 엔티티 타입: TYPE(m) = Member ( 상속관계에서 사용 )



조건식 - CASE 식

기본 case 식

```sql
select
	case when m.age <= 10 then '학생요금'
			 when m.age > 60 then  '경로요금'
			 else '일반요금'
	end
from Member m
```



조건 case 식

- COALESCE: 하나씩 조회해서 null이 아니면 반환
- NULLIF: 두 값이 같으면 null 반환, 다르면 첫번째 값 반환



### JPQL 기본함수

- CONCAT
- SUBSTRING
- TRIM
- LOWER, UPPER
- LENGTH
- LOCATE
- ABS, SQRT, MOD
- SIZE, INDEX(JPA 용도)