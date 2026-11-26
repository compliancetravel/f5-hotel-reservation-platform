"title": "ETG API v3",
        "contact": {},
        "version": "3.0.0"
    },
    "host": "https://api.ratehawk.com",
    "paths": {
        "/api/b2b/v3/general/contract/data/info": {
            "get": {
                "security": [
                    {
                        "BasicAuth": []
                    }
                ],
                "description": "Returns contract data info from Partner API.",
                "produces": [
                    "application/json"
                ],
                "tags": [
                    "general"
                ],
                "summary": "Get contract data info",
                "operationId": "b2b-v3-general-contract-data-info",
                "responses": {
                    "200": {
                        "description": "Successful response",
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/definitions/proxy.JSONResponse"
                                },
                                {
                                    "type": "object",
                                    "properties": {
                                        "data": {
                                            "$ref": "#/definitions/proxy.JSONBody"
                                        }
                                    }
                                }
                            ]
                        }
                    }
                }
            }
        },
        "/api/b2b/v3/general/document/closing_documents/download": {
            "get": {
                "security": [
                    {
                        "BasicAuth": []
                    }
                ],
                "description": "Downloads closing documents from Partner API.",
                "produces": [
                    "application/octet-stream"
                ],
                "tags": [
                    "general"
                ],
                "summary": "Download closing documents",
                "operationId": "b2b-v3-general-closing-documents-download",
                "parameters": [
                    {
                        "type": "string",
                        "description": "JSON object with package_id (integer) and seal (boolean)",
                        "name": "data",
                        "in": "query",
                        "required": true
                    }
                ],
                "responses": {
                    "200": {
                        "description": "Document file",
                        "schema": {
                            "type": "file"
                        }
                    }
                }
            }
        },
        "/api/b2b/v3/general/document/closing_documents/info": {
            "get": {
                "security": [
                    {
                        "BasicAuth": []
                    }
                ],
                "description": "Returns closing documents info from Partner API.",
                "produces": [
                    "application/json"
                ],
                "tags": [
                    "general"
                ],
                "summary": "Get closing documents info",
                "operationId": "b2b-v3-general-closing-documents-info",
                "parameters": [
                    {
                        "type": "string",
                        "description": "JSON object with optional agreement_numbers (string array), issue_date (date), and order_ids (integer array)",
                        "name": "data",
                        "in": "query",
                        "required": true
                    }
                ],
                "responses": {
                    "200": {
                        "description": "Successful response",
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/definitions/proxy.JSONResponse"
                                },
                                {
                                    "type": "object",
                                    "properties": {
                                        "data": {
                                            "$ref": "#/definitions/proxy.JSONBody"
                                        }
                                    }
                                }
                            ]
                        }
                    }
                }
            }
        },
        "/api/b2b/v3/general/financial/info": {
            "get": {
                "security": [
                    {
                        "BasicAuth": []
                    }
                ],
                "description": "Returns financial info from Partner API.",
                "produces": [
                    "application/json"
                ],
                "tags": [
                    "general"
                ],
                "summary": "Get financial info",
                "operationId": "b2b-v3-general-financial-info",
                "responses": {
                    "200": {
                        "description": "Successful response",
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/definitions/proxy.JSONResponse"
                                },
                                {
                                    "type": "object",
                                    "properties": {
                                        "data": {
                                            "$ref": "#/definitions/proxy.JSONBody"
                                        }
                                    }
                                }
                            ]
                        }
                    }
                }
            }
        },
        "/api/b2b/v3/hotel/custom/dump": {
            "post": {
                "security": [
                    {
                        "BasicAuth": []
                    }
                ],
                "description": "Returns a download link for a custom hotel dump.",
                "consumes": [
                    "application/json"
                ],
                "produces": [
                    "application/json"
                ],
                "tags": [
                    "hotel"
                ],
                "summary": "Get hotel custom dump link",
                "operationId": "b2b-v3-hotel-custom-dump",
                "parameters": [
                    {
                        "description": "Parameters",
                        "name": "data",
                        "in": "body",
                        "required": true,
                        "schema": {
                            "$ref": "#/definitions/info_dump.CustomDumpSwaggerRequest"
                        }
                    }
                ],
                "responses": {
                    "200": {
                        "description": "Successful response",
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/definitions/info_dump.DumpJSONResponse"
                                },
                                {
                                    "type": "object",
                                    "properties": {
                                        "data": {
                                            "$ref": "#/definitions/info_dump.InfoDumpResponse"
                                        }
                                    }
                                }
                            ]
                        }
                    }
                }
            }
        },
        "/api/b2b/v3/hotel/incremental_reviews/dump": {
            "post": {
                "security": [
                    {
                        "BasicAuth": []
                    }
                ],
                "description": "Returns a download link for the incremental hotel reviews dump.",
                "consumes": [
                    "application/json"
                ],
                "produces": [
                    "application/json"
                ],
                "tags": [
                    "hotel"
                ],
                "summary": "Get hotel incremental reviews dump link",
                "operationId": "b2b-v3-hotel-incremental-reviews-dump",
                "parameters": [
                    {
                        "description": "Parameters",
                        "name": "data",
                        "in": "body",
                        "required": true,
                        "schema": {
                            "$ref": "#/definitions/info_dump.LanguageDumpRequest"
                        }
                    }
                ],
                "responses": {
                    "200": {
                        "description": "Successful response",
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/definitions/info_dump.DumpJSONResponse"
                                },
                                {
                                    "type": "object",
                                    "properties": {
                                        "data": {
                                            "$ref": "#/definitions/info_dump.InfoDumpResponse"
                                        }
                                    }
                                }
                            ]
                        }
                    }
                }
            }
        },
        "/api/b2b/v3/hotel/info": {
            "post": {
                "security": [
                    {
                        "BasicAuth": []
                    }
                ],
                "consumes": [
                    "application/json"
                ],
                "produces": [
                    "application/json"
                ],
                "summary": "Get hotel info by hid or id",
                "operationId": "b2b-v3-hotel-info",
                "parameters": [
                    {
                        "description": "Parameters",
                        "name": "data",
                        "in": "body",
                        "required": true,
                        "schema": {
                            "$ref": "#/definitions/info.HotelInfoRequest"
                        }
                    }
                ],
                "responses": {
                    "200": {
                        "description": "OK",
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/definitions/v3.Response"
                                },
                                {
                                    "type": "object",
                                    "properties": {
                                        "data": {
                                            "$ref": "#/definitions/hotel_content_by_ids.HotelContentWithImages"
                                        }
                                    }
                                }
                            ]
                        }
                    }
                }
            }
        },
        "/api/b2b/v3/hotel/info/dump": {
            "post": {
                "security": [
                    {
                        "BasicAuth": []
                    }
                ],
                "description": "Returns a download link for the hotel info dump.",
                "consumes": [
                    "application/json"
                ],
                "produces": [
                    "application/json"
                ],
                "tags": [
                    "hotel"
                ],
                "summary": "Get hotel info dump link",
                "operationId": "b2b-v3-hotel-info-dump",
                "parameters": [
                    {
                        "description": "Parameters",
                        "name": "data",
                        "in": "body",
                        "required": true,
                        "schema": {
                            "$ref": "#/definitions/info_dump.InfoInventoryDumpRequest"
                        }
                    }
                ],
                "responses": {
                    "200": {
                        "description": "Successful response",
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/definitions/info_dump.DumpJSONResponse"
                                },
                                {
                                    "type": "object",
                                    "properties": {
                                        "data": {
                                            "$ref": "#/definitions/info_dump.InfoDumpResponse"
                                        }
                                    }
                                }
                            ]
                        }
                    }
                }
            }
        },
        "/api/b2b/v3/hotel/info/incremental_dump": {
            "post": {
                "security": [
                    {
                        "BasicAuth": []
                    }
                ],
                "description": "Returns a download link for the incremental hotel info dump.",
                "consumes": [
                    "application/json"
                ],
                "produces": [
                    "application/json"
                ],
                "tags": [
                    "hotel"
                ],
                "summary": "Get hotel incremental info dump link",
                "operationId": "b2b-v3-hotel-info-incremental-dump",
                "parameters": [
                    {
                        "description": "Parameters",
                        "name": "data",
                        "in": "body",
                        "required": true,
                        "schema": {
                            "$ref": "#/definitions/info_dump.InfoIncrementalInventoryDumpRequest"
                        }
                    }
                ],
                "responses": {
                    "200": {
                        "description": "Successful response",
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/definitions/info_dump.DumpJSONResponse"
                                },
                                {
                                    "type": "object",
                                    "properties": {
                                        "data": {
                                            "$ref": "#/definitions/info_dump.InfoDumpResponse"
                                        }
                                    }
                                }
                            ]
                        }
                    }
                }
            }
        },
        "/api/b2b/v3/hotel/order/booking/finish": {
            "post": {
                "security": [
                    {
                        "BasicAuth": []
                    }
                ],
                "consumes": [
                    "application/json"
                ],
                "produces": [
                    "application/json"
                ],
                "summary": "Booking finish",
                "operationId": "b2b-v3-booking-finish",
                "parameters": [
                    {
                        "description": "Parameters",
                        "name": "data",
                        "in": "body",
                        "required": true,
                        "schema": {
                            "$ref": "#/definitions/booking_finish.Request"
                        }
                    }
                ],
                "responses": {
                    "200": {
                        "description": "OK",
                        "schema": {
                            "$ref": "#/definitions/v3.Response"
                        }
                    }
                }
            }
        },
        "/api/b2b/v3/hotel/order/booking/finish/status": {
            "post": {
                "security": [
                    {
                        "BasicAuth": []
                    }
                ],
                "description": "Finish booking status",
                "consumes": [
                    "application/json"
                ],
                "produces": [
                    "application/json"
                ],
                "summary": "Booking Finish Status",
                "operationId": "b2b-order-booking-finish-status",
                "parameters": [
                    {
                        "description": "Parameters",
                        "name": "data",
                        "in": "body",
                        "required": true,
                        "schema": {
                            "$ref": "#/definitions/booking_status.Request"
                        }
                    }
                ],
                "responses": {
                    "200": {
                        "description": "OK",
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/definitions/v3.Response"
                                },
                                {
                                    "type": "object",
                                    "properties": {
                                        "data": {
                                            "$ref": "#/definitions/booking_status.Response"
                                        }
                                    }
                                }
                            ]
                        }
                    }
                }
            }
        },
        "/api/b2b/v3/hotel/order/booking/form": {
            "post": {
                "security": [
                    {
                        "BasicAuth": []
                    }
                ],
                "consumes": [
                    "application/json"
                ],
                "produces": [
                    "application/json"
                ],
                "summary": "Booking form",
                "operationId": "b2b-v3-booking-form",
                "parameters": [
                    {
                        "description": "Parameters",
                        "name": "data",
                        "in": "body",
                        "required": true,
                        "schema": {
                            "$ref": "#/definitions/booking_form.Request"
                        }
                    }
                ],
                "responses": {
                    "200": {
                        "description": "OK",
                        "schema": {
                            "allOf": [
                                {
                                    "$ref": "#/definitions/v3.Response"
                          