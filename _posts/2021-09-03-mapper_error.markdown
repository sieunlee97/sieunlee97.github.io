---
title: XML fragments parsed from previous mappers does not contain value for ~
categories:
- Error
last_modified_at: 2021-09-03T14:00:00+09:00
toc: true
---

## XML fragments parsed from previous mappers does not contain value for ~

```
XML fragments parsed from previous mappers does not contain value for commonMapper.search java.lang.IllegalArgumentException: XML fragments parsed from previous mappers does not contain value for commonMapper.search
```

boardMapper.xml 파일에 commonMapper.xml 파일에 있는 쿼리를 include하는 과정에서 에러가 발생했다.

### 수정 전
- **boardMapper.xml**

```xml
<select id="selectBoardTotalCount" parameterType="BoardDTO" resultType="int">
		SELECT 
				count(*) 
		FROM 	
				tbl_board
		WHERE
				<include refid="commonMapper.search" />
	</select>
```

- **commonMapper.xml**

```xml
<!-- MySQL 검색 -->
<mapper namespace="mappers.commonMapper">
	<sql id="search">
		<if test="searchKeyword != null and searchKeyword != ''">
			<choose>
				<when test="searchType != null and searchType != ''">
					<choose>
						<when test="'title'.equals(searchType)">
							AND title LIKE CONCAT('%', #{searchKeyword}, '%')
						</when>

						<when test="'writer'.equals(searchType)">
							AND writer LIKE CONCAT('%', #{searchKeyword}, '%')
						</when>
					</choose>
				</when>
				<otherwise>
					AND
						(
							title LIKE CONCAT('%', #{searchKeyword}, '%')
							OR writer LIKE CONCAT('%', #{searchKeyword}, '%')
						)
				</otherwise>
			</choose>
		</if>
	</sql>
</mapper>
```

- 원인은 두가지

1. commonMapper.xml의 네임스페이스는 mappers.commonMapper라고 설정했는데 include할 때 commonMapper라고만 명시했다.
2. boardMapper에 include할 때 where절 다음에 1=1을 써주지 않았다.


### 수정 후
- **boardMapper.xml**
```xml
<select id="selectBoardTotalCount" parameterType="BoardDTO" resultType="int">
		SELECT 
				count(*) 
		FROM 	
				tbl_board
		WHERE
				1=1
				<include refid="mappers.commonMapper.search" />
	</select>
```


