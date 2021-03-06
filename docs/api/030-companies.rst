API - Companies calls
=====================

.. Tip:: Test all of those requests in our API-Explorer_.

.. _API-Explorer: https://v2.app-arena.com/apigility/swagger/API-v1#!/instance

/companies
----------

.. _company:

.. http:method:: POST /api/v1/companies


.. http:response:: Example request body

    .. sourcecode:: js

        {
            "name"		:"New App-Arena customer. {{$timestamp}}",
            "subdomain"	        :"apparena_customer_{{$timestamp}}",
            "address1"	        :"My street 1",
            "address2"	        :"My street 2",
            "zip"		:"12345",
            "city"		:"My city",
            "country"		:"DE",
            "logo"		:"https://app-manager.s3.amazonaws.com/apps/models/3/0/4/0/de_DE/AppArena_Logo_aufweiss300x80_1413369016_0.png",
            "color1"		:"#478AB8",
            "color2"		:"#2D343D",
            "font"		:"helvetica-neue"
        }



    :data string name: (Required) Name of the company
    :data integer parent_id: (Optional) ID of the company whos customer the newly created company should be like
    :data string subdomain: (Required) Subdomain for all apps the company will create
    :data string address1: (Optional) Address field 1, e.g. Street 1
    :data string address2: (Optional) Address field 2, e.g. Street 2
    :data string zip: (Optional) Zip code
    :data string city: (Optional) City
    :data string country: (Optional) Two letter country code http://en.wikipedia.org/wiki/ISO3166-1alpha-2
    :data string logo: (Optional) Url to the company logo
    :data string color1: (Optional) Primary company color
    :data string color2: (Optional) Secondary company color
    :data string font: (Optional) Company font name

.. http:response:: Example response body

    .. sourcecode:: js

        {
            "address1": "My street 1",
            "address2": "My street 2",
            "city": "My city",
            "color1": "#478AB8",
            "color2": "#2D343D",
            "country": "DE",
            "id": 440,
            "logo": "https:\/\/app-manager.s3.amazonaws.com\/apps\/models\/3\/0\/4\/0\/de_DE\/AppArena_Logo_aufweiss300x80_1413369016_0.png",
            "name": "New App-Arena customer. 1430140889",
            "parent_id": 1,
            "subdomain": "apparena_customer_1430140889",
            "timestamp": 1430140930,
            "zip": "12345",
            "_links": {
                "self": {
                    "href": "https:\/\/v2.app-arena.com\/api\/v1\/companies\/440"
                }
            }
        }

.. http:method:: GET /api/v1/companies


.. http:response:: Example request body

    .. sourcecode:: js

        {
            "_links": {
                "self": {
                    "href": "https:\/\/v2.app-arena.com\/api\/v1\/companies?page=1"
                },
                "first": {
                    "href": "https:\/\/v2.app-arena.com\/api\/v1\/companies"
                },
                "last": {
                    "href": "https:\/\/v2.app-arena.com\/api\/v1\/companies?page=1"
                }
        },
        "_embedded": {
            "data": [
                {  ... },
                {
                    "id": 1,
                    "name": "iConsultants GmbH",
                    "subdomain": "app-arena",
                    "address1": "Kleingedankstr. 12",
                    "zip": "50677",
                    "city": "KÃ¶lle",
                    "country": "DE",
                    "logo": "https:\/\/app-manager.s3.amazonaws.com\/apps\/models\/3\/0\/4\/0\/de_DE\/AppArena_Logo_aufweiss300x80_1413369016_0.png",
                    "color1": "#478AB8",
                    "color2": "#2D343D",
                    "users": { },
                    "_links": {
                        "self": {
                            "href": "https:\/\/v2.app-arena.com\/api\/v1\/companies\/1"
                        }
                    }
                }
                {  ... },
            ]
        }

`Parameter documentation of the companies. <../api/030-companies.html#company>`_

/companies/:company_id
----------------------

.. http:method:: GET /api/v1/companies/:company_id

    :arg company_id: id of the company.


.. http:response:: Example request body

    .. sourcecode:: js

        {
            "id": 363,
            "name": "New App-Arena customer. 1429097807",
            "subdomain": "apparena_customer_1429097807",
            "address1": "My street 1",
            "address2": "My street 2",
            "zip": "12345",
            "city": "My city",
            "country": "DE",
            "logo": "https:\/\/app-manager.s3.amazonaws.com\/apps\/models\/3\/0\/4\/0\/de_DE\/AppArena_Logo_aufweiss300x80_1413369016_0.png",
            "color1": "#478AB8",
            "color2": "#2D343D",
            "_links": {
                "self": {
                    "href": "https:\/\/v2.app-arena.com\/api\/v1\/companies\/363"
                }
            }
        }

`Parameter documentation of the companies. <../api/030-companies.html#company>`_


.. http:method:: PUT /api/v1/companies/:company_id

    :arg company_id: id of the company.


.. http:response:: Example request body

    .. sourcecode:: js

        {
            "name"          :"Updated New Company Name _{{$timestamp}}",
            "subdomain"     :"updated_my_subdomain_{{$timestamp}}",
            "address1"	    :"Updated My street 1",
            "address2"	    :"Updated My street 2",
            "zip"	    :"11112345",
            "city"	    :"Updated My city",
            "country"	    :"AT",
            "logo"	    :"https://app-manager.s3.amazonaws.com/apps/models/3/0/4/0/de_DE/AppArena_Logo_aufweiss300x80_1413369016_0.png",
            "color1"	    :"#111111",
            "color2"	    :"#222222",
            "font"	    :"verdana"
        }

    :data string name: (Required) Name of the company
    :data string subdomain: (Optional) Subdomain for all apps the company will create
    :data string address1: (Optional) Address field 1, e.g. Street 1
    :data string address2: (Optional) Address field 1, e.g. Street 2
    :data string zip: (Optional) Zip code
    :data string city: (Optional) city
    :data string country: (Optional) Two letter country code http://en.wikipedia.org/wiki/ISO3166-1alpha-2
    :data object corporate_identity: (Optional) Corporate Identity configuration for faster app setup (values will be used as default settings, when creating apps)
    :data string logo: (Optional) Url to the company logo
    :data string color1: (Optional) Primary company color
    :data string color2: (Optional) Secondary company color
    :data string font: (Optional) Company font name

.. http:response:: Example response body

    .. sourcecode:: js

        {
            "address1": "Updated My street 1",
            "address2": "Updated My street 2",
            "city": "Updated My city",
            "color1": "#111111",
            "color2": "#222222",
            "country": "AT",
            "id": 440,
            "logo": "https:\/\/app-manager.s3.amazonaws.com\/apps\/models\/3\/0\/4\/0\/de_DE\/AppArena_Logo_aufweiss300x80_1413369016_0.png",
            "name": "Updated New Company Name_1430141082",
            "parent_id": 1,
            "subdomain": "updated_my_subdomain_1430141082",
            "timestamp": 1430141123,
            "zip": "11112345",
            "_links": {
                "self": {
                    "href": "https:\/\/v2.app-arena.com\/api\/v1\/companies\/440"
                }
            }
        }


.. http:method:: DELETE /api/v1/companies/:company_id

`Successful DELETE requests will return HTTP-Status code 204. <../api/001-index.html#codes>`_

/companies/:company_id/customers
--------------------------------

.. http:method:: GET /api/v1/companies/:company_id/customers

    :arg company_id: id of the company.


.. http:response:: Example request body

    .. sourcecode:: js

        {
            "_links": {
                "self": {
                    "href": "https:\/\/v2.app-arena.com\/api\/v1\/companies\/383\/customers"
                }
            },
            "_embedded": {
                "data": [
                    {
                        "id": 363,
                        "name": "New App-Arena customer. 1429097807",
                        "subdomain": "apparena_customer_1429097807",
                        "address1": "My street 1",
                        "address2": "My street 2",
                        "zip": "12345",
                        "city": "My city",
                        "country": "DE",
                        "logo": "https:\/\/app-manager.s3.amazonaws.com\/apps\/models\/3\/0\/4\/0\/de_DE\/AppArena_Logo_aufweiss300x80_1413369016_0.png",
                        "color1": "#478AB8",
                        "color2": "#2D343D",
                        "_links": {
                            "self": {
                                "href": "https:\/\/v2.app-arena.com\/api\/v1\/companies\/363"
                            }
                        }
                    }
                ]
            },
            "page_count": 0,
            "page_size": 25,
            "total_items": 0
        }

`Parameter documentation of the companies. <../api/030-companies.html#company>`_

/companies/:company_id/instances
--------------------------------

.. http:method:: GET /api/v1/companies/:company_id/instances

    :arg company_id: id of the company.


.. http:response:: Example request body

    .. sourcecode:: js

        {
            "_links": {
                "self": {
                    "href": "https:\/\/v2.app-arena.com\/api\/v1\/companies\/383\/instances"
                }
            },
            "_embedded": {
                "data": [
                    {
                        "active": 1,
                        "base_url": "https:\/\/adventskranz.onlineapp.co\/",
                        "description": "The description of my new instance.",
                        "id": 9627,
                        "lang_tag": "en_US",
                        "m_id": 299,
                        "name": "New Instance 1427295997",
                        "template_id": 780,
                        "timestamp": 1427296778,
                        "_links": {
                            "self": {
                                "href": "https:\/\/v2-stage.app-arena.com\/api\/v1\/instances\/9627"
                            }
                        }
                    }
                ]
            },
            "page_count": 0,
            "page_size": 25,
            "total_items": 0
        }

`Link to the parameter documentation. <../api/090-instances.html#instance_object>`_

/companies/:company_id/users
----------------------------

.. http:method:: GET /api/v1/companies/:company_id/users

    :arg company_id: id of the company.


.. http:response:: Example request body

    .. sourcecode:: js

        {
            "_links": {
                "self": {
                    "href": "https:\/\/v2.app-arena.com\/api\/v1\/companies\/383\/users"
                }
            },
            "_embedded": {
                "data": [
                    {
                        "id": 8012,
                        "username": "user-1429943426",
                        "password": "$2y$15$6pE0VJ0CPHrnTzyx49HBjOtTQ4ywPl2CGgoewZLVV3yXKKomTyK\/C",
                        "email": "extremterro@outlook.de",
                        "displayName": null,
                        "lang_tag": "de_DE",
                        "state": 1,
                        "roles": [
                            "user",
                            "admin"
                        ],
                        "company_id": 427,
                        "_links": {
                            "self": {
                                "href": "https:\/\/v2.app-arena.com\/api\/v1\/companies\/427\/users\/8012"
                            }
                        }
                    }
                ]
            },
            "page_count": 1,
            "page_size": 25,
            "total_items": 1
        }

    :data string id: ID of the User
    :data string username: Username created by the User
    :data string password: Password for the User
    :data string email: Email of the current User
    :data string displayName: Username which is displayed
    :data string lang_tag: Language of the current User
    :data int state: (NOCH EINFÜGEN)
    :data string roles: Die dem User zugeteilte Rolle z.B. Admin oder User
    :data int company_id: ID of the company of the User



