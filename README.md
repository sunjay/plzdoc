# plzdoc

Generates documentation.

## Process

1. Take in a glob pattern of files or multiple glob patterns or filenames
2. Read each file and parse out the JSDoc docstrings as well as the associated metadata (search the tree around the comment)
  * JSDoc docstrings start with `*`
    ```javascript
    /**
     * @param {Foo} foo - Does something
     */
    ```
3. Use doctrine to parse the JSDoc comment and use the surrounding function definitions to fill in missing documentation (function name, undocumented parameters)
4. Use the current module minus some base directory to figure out module names
5. Output a JSON format that contains the complete JSDoc information for every module with all the inferred information
6. Use the JSON output to generate markdown
7. Combine the output markdown as well as any other specified markdown files to generate
   documentation and a static site using either jekyll or metalsmith

Output errors with the file and LOC where the error occurred.

Should support combining documentation with existing prose markdown files so the
generated markdown seamlessly works with the JSDoc documentation.

Support just a subset of JSDoc syntax for now
