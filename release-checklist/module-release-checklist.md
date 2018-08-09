# MajiFix Module Release Checklist

> NOTE: Make sure all tests are running before committing your changes

## Update Dependencies

- [ ] Update faker dev dependency to use **@benmaruchu/faker**
- [ ] Update all MajiFix modules used to latest version of **@codetanzania/majifix-{module-name}**
- [ ] Update other dependencies
- [ ] Fix Http router specs to use api version in URL from app router
- [ ] Remove body parser in dev dependency

## Project Structure

- [ ] Make sure .npmignore exist and it ignores right files i.e examples, docs
- [ ] Make sure .editorconfig exist

## Files to crosscheck

### README.md

- [ ] Use standard formatting
- [ ] Update Requirements for node to match engines in package.json
- [ ] Update installation instructions
- [ ] Update Usage to use new package name i.e **@codetanzania/majifix-{module-name}**
- [ ] Fix any typos
- [ ] Update Node engine minimum version
- [ ] Update Mongoose version

### CHANGELOG.md

- [ ] Add release version and date in the format **v1.0.0 / yyyy-mm-dd**
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
    	   "node": ">=8.11.1",
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
- [ ] Make sure the code organization is right
- [ ] For local constants should be under local constant comment

### .router.js

> *if there is router file*

- [ ] Fix any typos
- [ ] Update api version
- [ ] Make sure all routes are well documented
- [ ] Generate API documents

### .app.json

> *if there is app.json file*

- [ ] Make sure the details are correct
- [ ] Make sure keywords resembles those from package.json

### .apidoc.json

> *if there is apidoc.json*

- [ ] Remove description field
- [ ] Remove version field
- [ ] Update sample url and url to use latest API url format

## Generate API Documentation

> *if applicable to the module*

- [ ] Run a command
  ```sh
  grunt doc
  ```
- [ ] Generate apidoc and crosscheck if everything is ok