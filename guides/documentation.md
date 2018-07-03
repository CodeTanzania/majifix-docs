# Documentation

In this project we try our level best to document the code so that the any new
developer can easily chip in and understand what is going on. We highly recommend
that you document any piece of code your are adding on this project.

Below is our recommendation when documenting routers in API modules. It is not
an exhaustive list but it will act as a starting point when we are documenting
routers for API modules.

## API Router Documentation

For API routes documentation we use [apidoc](http://apidocjs.com/) which generate
API documentation directly from block comments from the codes.

### Route Documentation

While documenting a route we recommend the comments to have the following

- @api
- @apiVersion
- @apiName
- @apiGroup
- @apiDescription
- @apiUse RequestHeaders
- @apiUse [*Success returned object format*]
- @apiUse RequestHeadersExample
- @apiUse [*Success response example*]
- @apiUse JWTError
- @apiUse JWTErrorExample
- @apiUse AuthorizationHeaderError
- @apiUse AuthorizationHeaderErrorExample

```js
/**
 * @api {get} /jurisdictions List Jurisdictions
 * @apiVersion 1.0.0
 * @apiName GetJurisdictions
 * @apiGroup Jurisdiction
 * @apiDescription Returns a list of jurisdictions
 * @apiUse RequestHeaders
 * @apiUse Jurisdictions
 *
 * @apiUse RequestHeadersExample
 * @apiUse JurisdictionsSuccessResponse
 * @apiUse JWTError
 * @apiUse JWTErrorExample
 * @apiUse AuthorizationHeaderError
 * @apiUse AuthorizationHeaderErrorExample
 */
router.get(PATH_LIST, function getJurisdictions(request, response, next) {
  /* ... */
}
```

For RequestHeaders, RequestHeadersExample, JWTError, JWTErrorExample,
AuthorizationHeaderError and AuthorizationHeaderErrorExample apidocs comments are
already defined in [majifix-common](https://github.com/CodeTanzania/majifix-common) module.
To use it you just have to include it in your apidoc build system.

This is an example of configuring apidoc grunt plugin to read apidoc comments from
[majifix-common](https://github.com/CodeTanzania/majifix-common)

```js
apidoc: {
    api: {
        src: ['node_modules/@codetanzania/majifix-common/lib', 'lib/'],
            dest: 'docs/',
                options: {
            debug: true,
                includeFilters: ['.*\\.js$'],
        }
    }
}
```

For Success returned object format and Success response example should be defined in the router file as shown in below examples:

```js
/**
 * @apiDefine Jurisdictions
 * @apiSuccess {Object[]} data List of jurisdictions
 * @apiSuccess {String} data._id Unique jurisdiction identifier
 * @apiSuccess {String} [data.jurisdiction = undefined] jurisdiction under
 * which this jurisdiction belongs
 * @apiSuccess {String} data.code Unique human readable coded name of
 * the jurisdiction. Used in deriving service request code
 * @apiSuccess {String} data.name Unique human readable name of the jurisdiction
 * @apiSuccess {String} data.phone Primary mobile phone number used to
 * contact jurisdiction
 * @apiSuccess {String} data.email Primary email address used to contact
 * jurisdiction direct
 * @apiSuccess {String} [data.website] Primary website url of the jurisdiction
 * @apiSuccess {String} [data.about] A brief summary about jurisdiction
 * if available i.e additional details that clarify what a jurisdiction do
 * @apiSuccess {String} [data.address] Human readable physical address of
 * jurisdiction office
 * @apiSuccess {String} [data.color] A color code(in hexadecimal format)
 * eg. #363636 used to differentiate jurisdictions visually
 * @apiSuccess {Point} [data.location] A center of jurisdiction. Its an
 * office reachable by citizen(or customer)
 * @apiSuccess {MultiPolygon} [data.boundaries] Jurisdiction boundaries.
 * Its mainly used for geo lookup of service request jurisdiction
 * based on its geo coordinates.
 * @apiSuccess {Date} data.createdAt Date when jurisdiction was created
 * @apiSuccess {Date} data.updatedAt Date when jurisdiction was last updated
 * @apiSuccess {Number} total Total number of jurisdiction
 * @apiSuccess {Number} size Number of jurisdiction returned
 * @apiSuccess {Number} limit Query limit used
 * @apiSuccess {Number} skip Query skip/offset used
 * @apiSuccess {Number} page Page number
 * @apiSuccess {Number} pages Total number of pages
 * @apiSuccess {Date} lastModified Date and time at which latest jurisdiction
 * was last modified
 */


/**
 * @apiDefine JurisdictionsSuccessResponse
 * @apiSuccessExample {json} Success-Response:
 *  {
 *    "data": [
 *    {
 *      "_id": "5aef42d59748e41e02e2a562",
 *      "jurisdiction": {
 *         "_id": "5af2aad4408ccb594b173f96",
 *         "code": "84105193",
 *         "name": "Faroe Islands"
 *      },
 *      "code": "66230485",
 *      "name": "Kunze and Sons",
 *      "phone": "1-964-200-3838 x5726",
 *      "email": "mazie_bayer@hotmail.com",
 *      "website": "vilma.net",
 *      "about": "Molestias culpa porro pariatur.",
 *      "address": "6552 Haven Prairie",
 *      "color": "#b32acc",
 *      "location": {
 *         "type": "Point",
 *         "coordinates": [
 *           -77.5707764925392,
 *           39.880937519031235
 *         ]
 *      },
 *      "boundaries": {
 *         "type": "MultiPolygon",
 *         "coordinates": [
 *         [
 *            [
 *              [
 *                -76.80207859497996,
 *                 55.69469494228919
 *              ],
 *              [
 *                -75.71404588095427,
 *                53.59198291229545
 *              ],
 *              [
 *                -73.49941546156064,
 *                47.7536674960849
 *              ],
 *              [
 *                -78.24692848453104,
 *                51.75424604090497
 *              ],
 *              [
 *                -77.96718998971203,
 *                43.532912808667284
 *              ],
 *              [
 *                -80.05583147381611,
 *                51.2655718114278
 *              ],
 *              [
 *                -87.10717890417094,
 *                49.55715210838287
 *              ],
 *              [
 *                -86.82247323878836,
 *                57.53161913076085
 *              ],
 *              [
 *                -81.00322721012589,
 *                56.68343367062641
 *              ],
 *              [
 *                -81.15080039041881,
 *                57.91444311426214
 *              ],
 *              [
 *                -76.80207859497996,
 *                55.69469494228919
 *              ]
 *             ]
 *          ],
 *        ]
 *      }
 *    ],
 *    "total": 5,
 *    "size": 1,
 *    "limit": 1,
 *    "skip": 0,
 *    "page": 1,
 *    "pages": 5,
 *    "lastModified": "2018-05-06T18:00:53.283Z"
 *  }
 */
```