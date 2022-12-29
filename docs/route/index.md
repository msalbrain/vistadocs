## API 

# POST /v1/login

+ Request (application/json; charset=utf-8)

    + Headers

            Cookie: _vista_platform_session=<vista token>

    + Body

            {
                "email": "chris@kanso.io",
                "password": "password"
            }

+ Response 200 (application/json; charset=utf-8)

    + Headers

            X-Content-Type-Options: nosniff
            X-Rack-CORS: miss; no-origin
            Etag: W/"5f2469bc79d1ccf2cb0554ccf3314e3c"
            X-Frame-Options: SAMEORIGIN
            X-XSS-Protection: 1; mode=block
            X-Request-Id: 4014520d-7732-4bf3-8d42-8f31a1b2e3ec
            X-Runtime: 0.175549
            Cache-Control: max-age=0, private, must-revalidate
            Transfer-Encoding: chunked

    + Body

            {"token":"<auth token>","needsOnboarding":false}


# POST /v1/register

+ Request (application/json; charset=utf-8)

    + Headers

            Cookie: _vista_platform_session=<vista token>

    + Body

            {
                "email": "kathy.villeda@example.com",
                "password": "password"
            }

+ Response 200 (application/json; charset=utf-8)

    + Headers

            X-Content-Type-Options: nosniff
            X-Rack-CORS: miss; no-origin
            Etag: W/"d37626fa2db73f508eb6fb5c7ce71ca3"
            X-Frame-Options: SAMEORIGIN
            X-XSS-Protection: 1; mode=block
            X-Request-Id: e7e24330-beac-48e4-abdb-3378d76fb214
            X-Runtime: 0.362156
            Cache-Control: max-age=0, private, must-revalidate
            Transfer-Encoding: chunked

    + Body

            {"token":"z89byAP37vpiouiZsPiAVmux","needsOnboarding":true}


# POST /v1/register

+ Request (application/json; charset=utf-8)

    + Headers

            Cookie: _vista_platform_session=<vista token>

    + Body

            {
                "email": "test@test.com",
                "password": "password"
            }

+ Response 401 (application/json; charset=utf-8)

    + Headers

            X-Content-Type-Options: nosniff
            X-Rack-CORS: miss; no-origin
            X-Frame-Options: SAMEORIGIN
            X-XSS-Protection: 1; mode=block
            X-Request-Id: 069b4a52-b0a1-4b57-831e-b1ff14ceef44
            X-Runtime: 0.623524
            Cache-Control: no-cache
            Transfer-Encoding: chunked

    + Body

            {"errors":[{"source":{"pointer":"/data/attributes/email"},"detail":"Email is already taken"}]}


# GET /v1/me

+ Request (application/json)

    + Headers

            Accept: application/json
            Cookie: _vista_platform_session=<vista token>
            Authorization: Token token=<auth token>



+ Response 200 (application/json; charset=utf-8)

    + Headers

            X-Runtime: 0.082517
            X-Xss-Protection: 1; mode=block
            Transfer-Encoding: chunked
            Cache-Control: max-age=0, private, must-revalidate
            X-Request-Id: fddcffef-bf97-43be-b16e-e143a19c2898
            X-Content-Type-Options: nosniff
            Etag: W/"e4675e989b64cd71d9e119f2d28a33cd"
            X-Frame-Options: SAMEORIGIN
            Last-Modified: Tue, 10 Oct 2017 13:45:05 GMT

    + Body

            {"id":2,"email":"chris@kanso.io","firstName":"Chris","lastName":"Edwards","name":"Chris Edwards","jobTitle":"null","company":"null","address":"null","memberId":"DnMZrZ","updatedAt":"2017-10-10T13:45:05.089Z","avatar":{"id":54,"largeUrl":"https://bucketeer-5fb9bfbe-c595-490e-8a9e-f78c342d65bf.s3-eu-west-1.amazonaws.com/uploads/photo/image/54/large_photo.jpg?X-Amz-Expires=600\u0026X-Amz-Date=20171011T094219Z\u0026X-Amz-Algorithm=AWS4-HMAC-SHA256\u0026X-Amz-Credential=AKIAID6MULWOTL2HSBXQ/20171011/eu-west-1/s3/aws4_request\u0026X-Amz-SignedHeaders=host\u0026X-Amz-Signature=0d33cb46c3b0a49e1a1ab80097a8a84bff20149afdd39aa40256453b7035c502","mediumUrl":"https://bucketeer-5fb9bfbe-c595-490e-8a9e-f78c342d65bf.s3-eu-west-1.amazonaws.com/uploads/photo/image/54/medium_photo.jpg?X-Amz-Expires=600\u0026X-Amz-Date=20171011T094219Z\u0026X-Amz-Algorithm=AWS4-HMAC-SHA256\u0026X-Amz-Credential=AKIAID6MULWOTL2HSBXQ/20171011/eu-west-1/s3/aws4_request\u0026X-Amz-SignedHeaders=host\u0026X-Amz-Signature=ab95bbbb0e5b94ea3d8ca803f33bb1ba9e4e2e4ea778f80d41921131c3053051","squareUrl":"https://bucketeer-5fb9bfbe-c595-490e-8a9e-f78c342d65bf.s3-eu-west-1.amazonaws.com/uploads/photo/image/54/square_photo.jpg?X-Amz-Expires=600\u0026X-Amz-Date=20171011T094219Z\u0026X-Amz-Algorithm=AWS4-HMAC-SHA256\u0026X-Amz-Credential=AKIAID6MULWOTL2HSBXQ/20171011/eu-west-1/s3/aws4_request\u0026X-Amz-SignedHeaders=host\u0026X-Amz-Signature=17479710095e896416fc016cff48cf1adb0b3b5123ffc629813b5de922d872c1","thumbUrl":"https://bucketeer-5fb9bfbe-c595-490e-8a9e-f78c342d65bf.s3-eu-west-1.amazonaws.com/uploads/photo/image/54/thumb_photo.jpg?X-Amz-Expires=600\u0026X-Amz-Date=20171011T094219Z\u0026X-Amz-Algorithm=AWS4-HMAC-SHA256\u0026X-Amz-Credential=AKIAID6MULWOTL2HSBXQ/20171011/eu-west-1/s3/aws4_request\u0026X-Amz-SignedHeaders=host\u0026X-Amz-Signature=797ae5b7d962b92571213aeced23aca81d219d9dc55a4e47c4248b349ae1a82f"}}


# PUT /v1/me

+ Request (application/x-www-form-urlencoded; charset=utf-8)

    + Headers

            Cookie: _vista_platform_session=<vista token>
            Authorization: Token token=<auth token>

    + Body

            user%5Bname%5D=Chris+Edwards



# GET /v1/partners

+ Request

    + Headers

            Cookie: _vista_platform_session=<vista token>
            Authorization: Token token=<auth token>



+ Response 200 (application/json; charset=utf-8)

    + Headers

            X-Runtime: 0.240713
            X-Xss-Protection: 1; mode=block
            Transfer-Encoding: chunked
            Cache-Control: max-age=0, private, must-revalidate
            X-Request-Id: 1519535a-24fc-4c8e-ab36-f7fba864b551
            X-Content-Type-Options: nosniff
            Etag: W/"9b185923d3c6d3ae7d173461a960d9f0"
            X-Frame-Options: SAMEORIGIN

    + Body

            [{"id":1,"name":"Park Hyatt New York","about":"Across the street from Carnegie Hall, this sleek hotel in Midtown is a minute's walk from 57th Street subway station and a mile from the Lincoln Centre","email":"","latitude":40.765605,"longitude":-73.97904,"categories":["Hotels"],"sharingProfile":false,"address":{"id":43,"label":null,"line1":"153 W 57th St","line2":"","town":"New York","county":"NY","postcode":"10019","country":"US","phone":"","latitude":"40.765605","longitude":"-73.97904"},"photo":{"id":57,"largeUrl":"https://bucketeer-5fb9bfbe-c595-490e-8a9e-f78c342d65bf.s3-eu-west-1.amazonaws.com/uploads/photo/image/57/large_Park_Hyatt_New_York_usn_2.jpg?X-Amz-Expires=600\u0026X-Amz-Date=20171018T110152Z\u0026X-Amz-Algorithm=AWS4-HMAC-SHA256\u0026X-Amz-Credential=AKIAID6MULWOTL2HSBXQ/20171018/eu-west-1/s3/aws4_request\u0026X-Amz-SignedHeaders=host\u0026X-Amz-Signature=e995f55a282fd2a6ce4271035a91ab20deceea76128b3ee60e4c1fcb43b141e1","mediumUrl":"https://bucketeer-5fb9bfbe-c595-490e-8a9e-f78c342d65bf.s3-eu-west-1.amazonaws.com/uploads/photo/image/57/medium_Park_Hyatt_New_York_usn_2.jpg?X-Amz-Expires=600\u0026X-Amz-Date=20171018T110152Z\u0026X-Amz-Algorithm=AWS4-HMAC-SHA256\u0026X-Amz-Credential=AKIAID6MULWOTL2HSBXQ/20171018/eu-west-1/s3/aws4_request\u0026X-Amz-SignedHeaders=host\u0026X-Amz-Signature=95680861779a39adcedd0b7c50e52dc0c8cedd2c538bd4a1d66808ae47a37e3a","squareUrl":"https://bucketeer-5fb9bfbe-c595-490e-8a9e-f78c342d65bf.s3-eu-west-1.amazonaws.com/uploads/photo/image/57/square_Park_Hyatt_New_York_usn_2.jpg?X-Amz-Expires=600\u0026X-Amz-Date=20171018T110152Z\u0026X-Amz-Algorithm=AWS4-HMAC-SHA256\u0026X-Amz-Credential=AKIAID6MULWOTL2HSBXQ/20171018/eu-west-1/s3/aws4_request\u0026X-Amz-SignedHeaders=host\u0026X-Amz-Signature=179a4651788d7cf9bbc0d75b73cefff44d14014762d07608c407ad6deffebc8e","thumbUrl":"https://bucketeer-5fb9bfbe-c595-490e-8a9e-f78c342d65bf.s3-eu-west-1.amazonaws.com/uploads/photo/image/57/thumb_Park_Hyatt_New_York_usn_2.jpg?X-Amz-Expires=600\u0026X-Amz-Date=20171018T110152Z\u0026X-Amz-Algorithm=AWS4-HMAC-SHA256\u0026X-Amz-Credential=AKIAID6MULWOTL2HSBXQ/20171018/eu-west-1/s3/aws4_request\u0026X-Amz-SignedHeaders=host\u0026X-Amz-Signature=fac106dd72c2cbf8cc49f28d14ece447cc6be00c10e2c0099dd64235537307ce"}}]


# POST /v1/partners/1/share

+ Request

    + Headers

            Cookie: _vista_platform_session=<vista token>
            Authorization: Token token=<auth token>



+ Response 204

    + Headers

            X-Content-Type-Options: nosniff
            X-Rack-CORS: miss; no-origin
            X-Frame-Options: SAMEORIGIN
            X-XSS-Protection: 1; mode=block
            X-Request-Id: 12481b72-4f85-4c34-b15a-78afabedd4b5
            X-Runtime: 0.327847
            Cache-Control: no-cache




# DELETE /v1/partners/1/revoke

+ Request

    + Headers

            Cookie: _vista_platform_session=<vista token>
            Authorization: Token token=<auth token>





# DELETE /v1/partners/revoke

+ Request

    + Headers

            Cookie: _vista_platform_session=<vista token>
            Authorization: Token token=<auth token>



+ Response 204

    + Headers

            X-Content-Type-Options: nosniff
            X-Rack-CORS: miss; no-origin
            X-Frame-Options: SAMEORIGIN
            X-XSS-Protection: 1; mode=block
            X-Request-Id: 62078460-f384-4cfb-8eb0-5990c8eea40f
            X-Runtime: 0.044358
            Cache-Control: no-cache




# GET /v1/categories

+ Request

    + Headers

            Cookie: _vista_platform_session=<vista token>
            Authorization: Token token=<auth token>



+ Response 200 (application/json; charset=utf-8)

    + Headers

            Last-Modified: Tue, 24 Oct 2017 13:46:07 GMT
            X-Runtime: 0.064698
            Set-Cookie: _vista_platform_session=Y0VJa1NlVTNPQWIzZXdDSFNLc1RFOGlIemllMUZnaHM2dzUwSEJVNTBSNk5ob1NPU3NGVDExUkRLc2ZUcVhLS1d6NEJIbVRzL2VrcEltVGVRb3dsdXpZY0FNUjlYVDJPTU1BRlZud0Q1SGlUVFMrTVVxVWo0WVpxQ1o4Q2dML2IyUXVCaHVnVUhJOTc0Snl5K1E4YVN3PT0tLUl1OG1aWXUyVEw5RnJaRGJHaURjSWc9PQ%3D%3D--8ba94682a0d98648f7d6cb4d6d6ac3785fdc15a9; path=/; HttpOnly
            X-XSS-Protection: 1; mode=block
            Transfer-Encoding: chunked
            Cache-Control: max-age=0, private, must-revalidate
            X-Request-Id: a60e1d64-8c16-4c49-b4f3-3dcee22c7fea
            X-Content-Type-Options: nosniff
            X-Rack-CORS: miss; no-origin
            Etag: W/"39062c091082b7fb83083db8c4ea041b"
            X-Frame-Options: SAMEORIGIN

    + Body

[
    {
        "id": 4222,
        "title": "General",
        "description": "Maecenas faucibus mollis interdum. Nulla vitae elit libero, a pharetra augue. Nulla vitae elit libero, a pharetra augue. Aenean lacinia bibendum nulla sed consectetur. Cras justo odio, dapibus ac facilisis in, egestas eget quam. Cras mattis consectetur purus sit amet fermentum.",
        "parentId": 4211,
        "hasChildren": false,
        "ancestry": "4211",
        "subtreeQuestionsCount": 6,
        "ignored": false,
        "position": 1,
        "initial": false,
        "visibilityConditions": null,
        "photo": {
            "id": 4107,
            "largeUrl": "http://assets.vista.test/uploads/photo/image/4107/large_440.jpeg",
            "mediumUrl": "http://assets.vista.test/uploads/photo/image/4107/medium_440.jpeg",
            "squareUrl": "http://assets.vista.test/uploads/photo/image/4107/square_440.jpeg",
            "thumbUrl": "http://assets.vista.test/uploads/photo/image/4107/thumb_440.jpeg"
        }
    },
    {
        "id": 4213,
        "title": "Parking",
        "description": "Maecenas faucibus mollis interdum. Nulla vitae elit libero, a pharetra augue. Nulla vitae elit libero, a pharetra augue. Aenean lacinia bibendum nulla sed consectetur. Cras justo odio, dapibus ac facilisis in, egestas eget quam. Cras mattis consectetur purus sit amet fermentum.",
        "parentId": 4211,
        "hasChildren": false,
        "ancestry": "4211",
        "subtreeQuestionsCount": 2,
        "ignored": false,
        "position": 2,
        "initial": false,
        "visibilityConditions": null,
        "photo": {
            "id": 4104,
            "largeUrl": "http://assets.vista.test/uploads/photo/image/4104/large_440.jpeg",
            "mediumUrl": "http://assets.vista.test/uploads/photo/image/4104/medium_440.jpeg",
            "squareUrl": "http://assets.vista.test/uploads/photo/image/4104/square_440.jpeg",
            "thumbUrl": "http://assets.vista.test/uploads/photo/image/4104/thumb_440.jpeg"
        }
    }
]

# GET /v1/questions

+ Request

    + Headers

            Cookie: _vista_platform_session=<vista token>
            Authorization: Token token=<auth token>



+ Response 200 (application/json; charset=utf-8)

    + Headers

            Last-Modified: Fri, 20 Oct 2017 15:10:59 GMT
            X-Runtime: 16.743717
            Set-Cookie: _vista_platform_session=SExnWlI2czdiNmRUOHF2WkJMcThteXkyMEw2Kzliekh2RFQ1eFY5MmpINXB0ZnJMcVhYb3FqTFA4UlZwZFJTdVRWK2ptVUgvdFkrQ1kvTHBjRFVELyt4SU1VZW5DRG5pQStTdVlpZ1JnaU40M0JBZDBTUXVpUGxvci81RDRUOVlBSkl2dkNvUWQreDV1M3V0a1g0My9BPT0tLURLR0xJeHNYajJ6cWd4MU85TlF2aHc9PQ%3D%3D--a3ffad65f936408151f08d22e03ac77aff229d92; path=/; HttpOnly
            X-XSS-Protection: 1; mode=block
            Transfer-Encoding: chunked
            Cache-Control: max-age=0, private, must-revalidate
            X-Request-Id: 72c8a29e-6574-4728-8603-896b313b621d
            X-Content-Type-Options: nosniff
            X-Rack-CORS: miss; no-origin
            Etag: W/"521fefadcabf9349305b98d53243afd6"
            X-Frame-Options: SAMEORIGIN

    + Body

            [
    {
        "id": 283,
        "title": "Eos porro sequi velit.?",
        "categoryId": 4222,
        "kind": "time",
        "lockingConditions": null,
        "intro": false,
        "allowsNote": true,
        "noteTitle": null,
        "visibilityConditions": [],
        "photo": null,
        "answers": []
    },
    {
        "id": 284,
        "title": "Error blanditiis et in et iure non laboriosam.?",
        "categoryId": 4222,
        "kind": "option",
        "lockingConditions": null,
        "intro": false,
        "allowsNote": true,
        "noteTitle": null,
        "visibilityConditions": [],
        "photo": null,
        "answers": [
            {
                "id": 551,
                "title": "Quia et repellat sit.",
                "description": "Dolores vel qui laudantium beatae eum et nemo. Explicabo inventore deserunt consequatur aut ipsam doloremque. Quo repellat fuga nobis atque. Officia vel libero. Velit non ratione sint odio enim fuga.",
                "photo": null
            },
            {
                "id": 550,
                "title": "Eaque inventore aut voluptas et placeat sit.",
                "description": "Aspernatur hic ea voluptas quidem quos. Commodi laboriosam dolores architecto facere eum deserunt ut. Voluptates et minima exercitationem dolores enim. Tempora sed fugit omnis et.",
                "photo": null
            },
            {
                "id": 549,
                "title": "Nihil aut blanditiis rerum harum animi incidunt voluptatem adipisci.",
                "description": "Repellendus aut autem voluptatem veniam. Suscipit enim labore dignissimos et. Occaecati dolor labore voluptas et sed.",
                "photo": null
            }
        ]
    }
]


# GET /v1/news

+ Request

    + Headers

            Cookie: _vista_platform_session=<vista token>
            Authorization: Token token=<auth token>



+ Response 200 (application/json; charset=utf-8)

    + Headers

            X-Runtime: 0.099705
            Set-Cookie: _vista_platform_session=<vista token>; path=/; HttpOnly
            X-XSS-Protection: 1; mode=block
            Transfer-Encoding: chunked
            Cache-Control: max-age=0, private, must-revalidate
            X-Request-Id: a4f77782-aa40-446d-9554-52e336b9f46c
            X-Content-Type-Options: nosniff
            X-Rack-CORS: miss; no-origin
            X-Frame-Options: SAMEORIGIN
            Etag: W/"657c4fa5eae94aa1fcfc41f72713078b"

    + Body

            [{"id":3,"title":"Reprehenderit quae rerum voluptatibus consequatur molestiae.","content":"Ut natus alias sit quas a. Nulla pariatur voluptatem esse labore explicabo ut soluta. Quaerat corrupti consequatur asperiores quam veniam animi reprehenderit. Neque et excepturi non consequatur iure dolore.","publishAt":"2017-10-25T14:44:11.965Z","headerImage":null},{"id":2,"title":"Consequatur architecto est quos.","content":"Quidem voluptates numquam. Eum dolor commodi ullam ducimus voluptatem. Sint cumque aut id ut quo. Error aut dolore ut non maxime. Tempora necessitatibus debitis alias omnis ad unde.","publishAt":"2017-10-25T14:44:01.694Z","headerImage":null},{"id":1,"title":"In et et rerum.","content":"Quas et voluptates qui reprehenderit. Fugit id molestiae exercitationem libero. At nihil consequatur soluta.","publishAt":"2017-10-25T14:42:52.127Z","headerImage":null}]


# GET /v1/sync

+ Request

    + Headers

            Cookie: _vista_platform_session=<vista token>
            Authorization: Token token=<auth token>



+ Response 200 (application/json; charset=utf-8)

    + Headers

            X-Runtime: 0.012769
            Set-Cookie: _vista_platform_session=QkdSYXI4YXVITU55SExTUWNqNzYybG5TTHZjellOUm1hVU1tVEF5QjZYcmlXVCtkY3NIZzJpekJ2czkrbVYycUlIOGFmdUJ0THMxOHViMTgyN04xV2t3WkxzYm5jUjNCY0FCcUliMWZ2OXJvQktxVndobUkyS2pmdjY5TmdwOVUwcHhzUnljSHNFd2JDaEFheGZhSjVnPT0tLUhxZjl5eVF3VEZ0SHd1c09aN3pYU0E9PQ%3D%3D--5ae00d544a9d7b536593a35d8502990225f7ef04; path=/; HttpOnly
            X-XSS-Protection: 1; mode=block
            Transfer-Encoding: chunked
            Cache-Control: max-age=0, private, must-revalidate
            X-Request-Id: 9b750da0-28fb-4fc8-91fe-888632876df6
            X-Content-Type-Options: nosniff
            X-Rack-CORS: miss; no-origin
            X-Frame-Options: SAMEORIGIN
            Etag: W/"cde515396cfa9a18a4df24f4ba428ae5"

    + Body

            {"answers":[{"questionId":23,"updatedAt":"2017-09-19T15:33:00.033Z"},{"questionId":25,"updatedAt":"2017-09-20T12:13:44.437Z"},{"questionId":34,"updatedAt":"2017-09-20T12:17:08.956Z"},{"questionId":26,"updatedAt":"2017-09-20T12:18:19.558Z"},{"questionId":36,"updatedAt":"2017-09-20T12:29:00.676Z"},{"questionId":27,"updatedAt":"2017-09-22T11:58:21.974Z"},{"questionId":28,"updatedAt":"2017-09-22T11:59:07.897Z"},{"questionId":30,"updatedAt":"2017-09-22T11:59:12.029Z"},{"questionId":32,"updatedAt":"2017-09-22T11:59:18.110Z"},{"questionId":29,"updatedAt":"2017-09-22T12:00:01.611Z"},{"questionId":33,"updatedAt":"2017-09-22T12:00:15.490Z"},{"questionId":31,"updatedAt":"2017-09-22T12:00:24.099Z"},{"questionId":35,"updatedAt":"2017-09-22T12:15:22.340Z"},{"questionId":19,"updatedAt":"2017-09-22T12:35:47.546Z"},{"questionId":20,"updatedAt":"2017-09-22T12:35:50.356Z"},{"questionId":21,"updatedAt":"2017-09-22T12:36:02.139Z"},{"questionId":22,"updatedAt":"2017-09-22T12:36:06.128Z"},{"questionId":37,"updatedAt":"2017-09-25T10:54:56.570Z"},{"questionId":38,"updatedAt":"2017-09-25T10:54:58.493Z"},{"questionId":24,"updatedAt":"2017-09-25T13:32:55.687Z"},{"questionId":39,"updatedAt":"2017-09-25T14:09:28.693Z"},{"questionId":40,"updatedAt":"2017-09-25T14:09:29.674Z"},{"questionId":41,"updatedAt":"2017-09-25T14:09:30.527Z"},{"questionId":44,"updatedAt":"2017-09-29T08:32:07.403Z"}]}


# POST /v1/sync

+ Request (application/json; charset=utf-8)

    + Headers

            Cookie: _vista_platform_session=<vista token>
            Authorization: Token token=<auth token>

    + Body

            {
                "update": [
                    {
                        "questionId": 23,
                        "values": "Online!",
                        "note": null
                    }
                ],
                "get": [
                    34,
                    26,
                    36
                ],
                "delete": [
                    24
                ],
                "add": [
                    {
                        "questionId": 24,
                        "values": "Less than $1000"
                    }
                ]
            }

+ Response 200 (application/json; charset=utf-8)

    + Headers

            X-Content-Type-Options: nosniff
            X-Rack-CORS: miss; no-origin
            Etag: W/"7a6c0435085bc365fd48af39a659c339"
            X-Frame-Options: SAMEORIGIN
            X-XSS-Protection: 1; mode=block
            X-Request-Id: 74d19483-7955-4cfd-995c-625bed55abd5
            X-Runtime: 0.664534
            Cache-Control: max-age=0, private, must-revalidate
            Transfer-Encoding: chunked

    + Body

            [{"id":15,"questionId":34,"values":"No","note":null,"synced":true},
            
            {"id":16,"questionId":26,"values":"Yes","note":null,"synced":true},
            
            {"id":18,"questionId":36,"values":"First floor","note":null "synced":true}
                ]


# POST /v1/categories/4222/ignore

+ Request

    + Headers

            Cookie: _vista_platform_session=<vista token>
            Authorization: Token token=<auth token>



+ Response 204

    + Headers

            X-Content-Type-Options: nosniff
            X-Rack-CORS: miss; no-origin
            X-Frame-Options: SAMEORIGIN
            X-XSS-Protection: 1; mode=block
            X-Request-Id: e30ae883-45c7-4e0b-a186-adc8347802b5
            X-Runtime: 0.016333
            Cache-Control: no-cache




# DELETE /v1/categories/4222/ignore

+ Request

    + Headers

            Cookie: _vista_platform_session=<vista token>
            Authorization: Token token=<auth token>



+ Response 204

    + Headers

            X-Content-Type-Options: nosniff
            X-Rack-CORS: miss; no-origin
            X-Frame-Options: SAMEORIGIN
            X-XSS-Protection: 1; mode=block
            X-Request-Id: db00018d-bd1a-4621-801d-300f2bb569f6
            X-Runtime: 0.014774
            Cache-Control: no-cache




# POST /v1/password/reset

+ Request (application/json; charset=utf-8)

    + Headers

            Cookie: _vista_platform_session=<vista token>
            Authorization: Token token=<auth token>

    + Body

            {
                "email": "foo"
            }

+ Response 400 (application/json; charset=utf-8)

    + Headers

            X-Content-Type-Options: nosniff
            X-Rack-CORS: miss; no-origin
            X-Frame-Options: SAMEORIGIN
            X-XSS-Protection: 1; mode=block
            X-Request-Id: ad3bcf39-eea9-4526-9ada-85e95c1afbbc
            X-Runtime: 0.007599
            Cache-Control: no-cache
            Transfer-Encoding: chunked

    + Body

            {"errors":[{"detail":"No user found for request"}]}


# PUT /v1/password/reset

+ Request (application/json; charset=utf-8)

    + Headers

            Cookie: _vista_platform_session=<vista token>
            Authorization: Token token=<auth token>

    + Body

            {
                "token": "bad",
                "password": "password",
                "password_confirmation": "password"
            }

+ Response 400 (application/json; charset=utf-8)

    + Headers

            X-Content-Type-Options: nosniff
            X-Rack-CORS: miss; no-origin
            X-Frame-Options: SAMEORIGIN
            X-XSS-Protection: 1; mode=block
            X-Request-Id: 4fb7572f-38c4-4a99-a033-e01466874fc6
            X-Runtime: 0.013222
            Cache-Control: no-cache
            Transfer-Encoding: chunked

    + Body

            {"errors":{"token":"Password reset token invalid"}}


