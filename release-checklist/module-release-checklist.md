# MAJIFIX MODULE RELEASE CHECKLIST

> NOTE: Make sure all tests are running before committing your changes

## Update Dependencies

- [ ] Update faker dev dependency to use **@benmaruchu/faker**
- [ ] Update all majifix modules used to latest version of **@codetanzania/majifix-{module-name}**
- [ ] Update other dependencies
- [ ] Fix Http router specs to use api version in URL from app router
- [ ] Remove body parser in dev dependency

## Project Structure

- [ ] Make sure .npmignore exist and it ignores right files
- [ ] Make sure .editorconfig exist

## Files to crosscheck

### README.md

- [ ] Use standard formatting
- [ ] Update Requirements for node to match engines in package.json
- [ ] Update Usage to use new package name
- [ ] Fix any typos

### CHANGELOG.md

- [ ] Add release version and date in the format **yyyy-mm-dd**
- [ ] add list of changes/features in the release

### package.json

- [ ] Update package name in package.json to use @codetanzania scope
- [ ] Update package version number
- [ ] Update keywords in package.json to be
	```json
		  "keywords": [
    		"codetanzania",
    		"majifix",
    		"majifix-module",
			  "<replace with module-name>",
			  "open311"
  	  ],
	```
- [ ] Update sandbox url to use new api version
- [ ] Add engines as
	```json
        "engines": {
    	   "node": ">=8.1.11",
    	   "npm": ">=5.6.0"
  		}
    ```

### .model.js

> *if there is model file*

#### jsdoc

- [ ] Crosscheck authors are there
- [ ] Make sure the version number is updated
- [ ] For block comments with separators use hyphens to show separations
  ```js
    /*
    *---------------------------------------------------------------------
    * Statics
    *---------------------------------------------------------------------
    */
  ```
- [ ] Make sure the formatting for jsdoc follow it's conventions
- [ ] Fix any typos

#### codes

- [ ] Make sure spacing between blocks in 2 lines
- [ ] Make sure the organization is right
- [ ] For local constants should be under local constant comment

### .router.js

> *if there is router file*

- [ ] Fix any typos
- [ ] Update api version
- [ ] Make sure all routes are well documented
