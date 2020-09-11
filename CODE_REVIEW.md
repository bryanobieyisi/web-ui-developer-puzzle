
# Code Review

## Problems 
1. Potential memory leak from observable in `ngOnInit()` in `libs/books/feature/src/lib/book-search/book-search.component.ts`. The observable should be unsubscribed from using `ngOnDestroy()` **--Fixed**

2. Files with different functions are grouped together in `libs/books/data-access/src/lib/+state`. Actions, reducer and selector files should be grouped according to their function and their reference undated everywhere

3. No type tags added in `nx.json` and defined in `tslint.json`. Tags should be added to control folder access between apps in a mono repo

4. This file `test-setup.ts` exists in both the `apps` and `libs` folders (`apps/okreads/browser/src/` and `libs/books/feature/src/`). It should be removed from `apps` and    should only exist in `libs` since it is shared.

5. Bad naming conviention of `fb: FormBuilder` in `libs/books/feature/src/lib/book-search/book-search.component.ts`. Avoid using single and double character name declaration. Give specific names to variables and methods **--Fixed**

6. Access modifiers like `private` are not used in class variables to encourage encapsulation. **--Fixed**

7. Lack of code documentation or comments to help make the code easy to read and understand




# Lighthouse

## Accessibilty Issues
1. Screen reader can't read the button in `libs/books/feature/src/lib/book-search` due to the button not having a proper identification. I fixed it by giving the button the        `aria-label` property of `searchButton`. **--Fixed**
2. Background and foreground colors did not have a sufficient contrast ratio. 
    Changed button `background-color: $pink-fix` in `app.component.scss` and `.empty{... color: $gray70}` in `book-search.component.scss`  **--Fixed**

## Manual Accessibilty Issues
1. No arial-label attribute in the search bar element in `libs/books/feature/src/lib/book-search/book-search.component.html`. **--Fixed**
2. No arial-label or role attribute in the book title `div`. **--Fixed**
3. No `alt` text in book cover image tag in `libs/books/feature/src/lib/book-search/book-search.component.html`. **--Fixed**

## SEO: Search Engine Optimzation
1. The website was not optimized for search engines. I fixed this by adding a meta description in `src/apps/okreads/browser/src/index.html`. **--Fixed**

## More Issues
* In mobile mode, screen content does not resize. Grid is not completely responsive. 
    Fixed by adding media queries to `libs/books/feature/src/lib/book-search/book-search.component.scss`.**--Fixed**

* Author does not show up in one of the cards





