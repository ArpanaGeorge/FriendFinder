# FriendFinder

https://friend-finder-arp.herokuapp.com/

### Overview

This is a compatibility-based "FriendFinder" application. This full-stack site will take in results from your users' surveys, then compare their answers with those from other users. The app will then display the name and picture of the user with the best overall match.

### Program Logic

1. Survey have 10 questions. Each answer is on a scale of 1 to 5 based on how much the user agrees or disagrees with a question.

2. `server.js` file has npm packages : `express` and `body-parser`.

3. `htmlRoutes.js` file include two routes:

   * A GET Route to `/survey` which display the survey page.
   * A default, catch-all route that leads to `home.html` which displays the home page.

4. `apiRoutes.js` file contains two routes:

   * A GET route with the url `/api/friends`. This is used to display a JSON of all possible friends.
   * A POST routes `/api/friends`. This is used to handle incoming survey results. This route is also used to handle the compatibility logic.

5. Saved application's data inside of `app/data/friends.js` as an array of objects.

6. Determined the user's most compatible friend using the following logic:

   * Converted each user's results into a simple array of numbers.
   * With that done, compared the difference between current  user's scores against those from other users, question by question. Added up the differences to calculate the totalDifference.
   * Used absolute value of the differences by using math.abs().
   * Find the closest match by finding the user with the least amount of difference by using Math.min().

7. Once found the current user's most compatible friend, displayed the result, both the name and picture of the closest match as a modal pop-up.
  