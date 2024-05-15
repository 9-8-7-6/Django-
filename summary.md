Django Document 重點
===

來源:https://docs.djangoproject.com/en/5.0/topics/db/models/


## Model(資料庫，透過ORM來實現用python語法就可以操作資料庫)

來源:https://docs.djangoproject.com/en/5.0/topics/db/models/

1. NULL = True，則可以NULL儲存，預設為False
2. blank = True，則可以空白值儲存，預設為False
3. Primary_key = True，也就是pk，預設為False，若設為True，可以把一個field設為primary key，例如id = models.BigAutoField(primary_key=True)
4. verbose name是一個filed可以human-readable的name
5. Relations
    1. Many-to-one relationships可以ForeignKey來做
    2. Many-to-many relationships直接把該model當作引述argument
    3. One-to-one relationships
6. Field命名規範
    1. 不能和pass,這些有其他功能的詞重複
    2. 底線不能超過一個
    3. 不能以底線結尾
7. Meta這個class不屬於filed的資料可以放入，例如ordering方式
8. method是給物件object使用的函數，除了__str__()不用特別呼叫

## Database transaction

來源:https://docs.djangoproject.com/en/5.0/topics/db/transactions/

1. Django用transactions、savepoint來確保ORM 
2. Transaction是的特性為ACID
    1. Atomicity:全部完成或是全部不要
    2. Consistency: 一致性的約束限制
    3. Isolation:每筆交易都不干擾彼此
    4. Durability:結果被永久保存(不是暫存)
3. Savepoint是把transaction切為更小單位，若失敗，允許回復小單位rollback(回滾)
4. atomic可以用
    1. decorator ![atomic-decorator](https://i.imgur.com/fIrlDvC.png)
    2. context manager ![atomic-context manager](https://i.imgur.com/MxtcOVu.png)
5. transaction只有commit(提交)或是rollback(回滾)

Form

來源:https://docs.djangoproject.com/en/5.0/topics/forms/
1. 需要action(目標url)、method(http方法)
2. 分為GET(像是唯獨模式) POST
3. 
