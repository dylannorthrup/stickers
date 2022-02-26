# Changelog

All notable changes to this project will be documented in this file.

## [1.1](https://github.com/76creates/stickers/compare/v1.0...v1.1) (2022-02-26)
### ⚠ BREAKING CHANGES
* Refactored `Table` to support sorting, some methods have changed most notably revolving around adding rows since now its taking [][]any instead of [][]string, initial `Table` is now closer to `TableSingleType[string]`
* Stickers now uses generics, so go1.18 is mandatory

### Fixes
* Fixed recalculation triggering when *FlexBoxCell or *FlexBoxRow is fetched from the FlexBox
* Small lexical changes and tidying up

### Features
* Sorting is now availible for `Table` and `TableSingleType`
* `Table` has been reformatted and now supports **sorting by type**, when `Table` is initialized each colum type is set to `string`, you can now update that using `SetType` method, types supported are located in interface `Ordered`
* Added `TableSingleType` type which locks row type to `string`, this makes it easier for user when adding rows as there is much less errors that can occurr as when using `Table` where all depends on a type
* Added method `OrderByColumn` which envokes sorting for column `n`, for now you cannot explicitly set sorting direction and its switching between `asc` and `desc` when you sort same column 
* Added method `GetCursorLocation` which returns `x`,`y` of the curent cursor location on the table
* Added error types `TableBadTypeError`, `TableRowLenError`, `TableBadCellTypeError`
* Minor preformace enhancements