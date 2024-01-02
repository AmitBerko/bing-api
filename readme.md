# Bing Image Creator API

## Overview

The API allows you to generate images based on a given prompt using Bing's image creator (Powered by Dalle-3).

## Initialization

### `BingApi(cookie: string)`

- **Parameters:**

  - `cookie` (string): The account's `_U` cookie value which is required for authentication.

  In order to obtain your `_U` cookie follow these steps:

  - Log in to [Bing Image Creator](https://bing.com/create)
  - Open the browser's developer tools (F12 or right-click and select "Inspect").
  - Navigate to the "Application / Storage" tab.
  - Click on **Cookies**, then search and copy the value of the `_U` cookie.

```js
const bingApi = new BingApi('Your _U Cookie Value')
```

## Create Images

### `createImages(prompt: string, isSlowMode: boolean): Promise<string[]>`

- **Parameters:**

  - `prompt` (string): The prompt for the image generation.
  - `isSlowMode` (boolean): A flag to indicate whether to use Slow Mode or not.

- **Usage:**

  ```js
  const imagesUrls = await bingApi.createImages('A cat in space', false)
  ```

- **Description:**
  Generates images based on the provided prompt. If `isSlowMode` is set to `true`, it uses Slow Mode, allowing the generation of prompts without consuming daily credits.

## Get Credits

### `getCredits(): Promise<string>`

- **Usage:**

  ```js
  const credits = await bingApi.getCredits()
  console.log(`Current credits: ${credits}`)
  ```

- **Returns:**
  A string representing the available credits for prompt generation.

- **Description:**
  Retrieves the number of the current amount of credits the account has.
