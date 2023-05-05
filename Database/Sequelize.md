# Sequelize

- Node.js 기반의 ORM

## literal()

- sub query를 작성하는데 raw query를 넣고 싶을 때 사용하는 함수.
- 쿼리문을 직접 넣기 때문에 보안에 취약할 수 있다.

```sql

Post.findAll({
    attributes: {
        include: [
            [
                sequelize.literal(`(
                    SELECT COUNT(*)
                    FROM reactions AS reaction
                    WHERE
                        reaction.postId = post.id
                        AND
                        reaction.type = "Laugh"
                )`),
                'laughReactionsCount'
            ]
        ]
    },
    order: [
        [sequelize.literal('laughReactionsCount'), 'DESC']
    ]
});

```

### reference

- https://sequelize.org/docs/v6/other-topics/sub-queries/
