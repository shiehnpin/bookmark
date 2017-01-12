FORMAT: 1A

[Slide](https://docs.google.com/presentation/d/1W5G7lemPaLOvz9bxVRCwEKB6nqizvJntIfszacd4uUw/edit?usp=sharing)
[SampleCode](https://github.com/shiehnpin/SimpleBookmark)

# bookmark

Bookmark 提供使用者新增/修改/刪除/取得書摘的RESTful API

## Bookmarks Collection [/bookmarks]

### List All Bookmarks [GET]

取得書摘列表

+ Response 200 (application/json)

        [
            {
                "id":1,
                "text":"這個家族的歷史不過是一系列無可改變的重覆，若不是輪軸在過程中必不可免地磨損，這旋轉的車輪將永遠滾動下去。"
            },
            {
                "id":2,
                "text":"所謂一步都沒有走出過內心的事情，在這個世界是不存在的。"
            }
        ]

### Create a New Bookmark [POST]

插入新的書摘

+ Request (application/json)

        {
            "text":"與怪物戰鬥的人，應當小心自己不要成為怪物。當你凝視深淵，深淵也凝視著你。"
        }

+ Response 201 (application/json)

    + Headers

            Location: /bookmarks/3

    + Body

            [
                {
                    "id":1,
                    "text":"這個家族的歷史不過是一系列無可改變的重覆，若不是輪軸在過程中必不可免地磨損，這旋轉的車輪將永遠滾動下去。"
                },
                {
                    "id":2,
                    "text":"所謂一步都沒有走出過內心的事情，在這個世界是不存在的。"
                },
                {
                    "id":3,
                    "text":"與怪物戰鬥的人，應當小心自己不要成為怪物。當你凝視深淵，深淵也凝視著你。"    
                }
            ]
            
            ## Bookmarks Collection [/bookmarks]

## Bookmarks item [/bookmarks/{id}]

### Edit Bookmark [PUT]

修改某個書摘

+ Request (application/json)

        {
            "text":"與Code戰鬥的人，應當小心自己不要成為Code。當你凝視Bug，Bug也凝視著你。"
        }

+ Response 200 (application/json)

    + Headers

            Location: /bookmarks/3

    + Body

            
            {
                "id":3,
                "text":"與Code戰鬥的人，應當小心自己不要成為Code。當你凝視Bug，Bug也凝視著你。"
            }
            
### Delete Bookmark [DELETE]

刪除某個書摘

+ Response 200
