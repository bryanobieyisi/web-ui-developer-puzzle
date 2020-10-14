
# Code Review
google (page load optimizations in angular) application laod performance in angular. that is check for unessarry dependency libraries
## Problems 
1. Potential memory leak from observable in `ngOnInit()` in `libs/books/feature/src/lib/book-search/book-search.component.ts`. The observable should be unsubscribed from using `ngOnDestroy()`
    The other solution would be to use `pipe()` with `takeUntil()` operator and a `Subject` to unsubscribe from the observable in `ngOnInit()`  **--Fixed**

2. --verify-- `/Users/chukwukaodinakaobieyisi/Documents/web-ui-developer-puzzle-master-prod/libs/books/feature/src/lib/total-count/total-count.component.scss` is empty so remove

3. No type tags added in `nx.json` and defined in `tslint.json`. Tags should be added to control folder access between apps in a mono repo

4. The method `searchExample()` in `book-search.component.ts` is unecessary because you can modify `searchBooks()` to do the same thing. **--Fixed**

5. Bad naming conviention of `fb: FormBuilder` in `libs/books/feature/src/lib/book-search/book-search.component.ts`. Avoid using single and double character name declaration. Give specific names to variables and methods **--Fixed**

6. -
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

* Author does not show up in one of the cards. And publisher does not show up in another. I believe this omission comes from the external google api where the books are being retrived from (`https://www.googleapis.com/books/`).
![](./screenshot1.png)
![](./screenshot2.png)





