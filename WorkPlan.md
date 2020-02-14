## What is the expected Team deliverable?
Four separate analyses of user data from Google / Spotify / Facebook APIs, visualised on a web-application written in FABLE(?)

Extension: Combination of our analyses to derive even more meaningful inferences.

Resources:
- [Google APIs](https://developers.google.com/apis-explorer)
- [Spotify APIs](https://developer.spotify.com/documentation/web-api/reference/users-profile/get-users-profile/)

## Questions (TO-DO)
1. [TC] We intend to use the type providers in FSharp.Data for parsing of JSON. Allowed?
2. [TC] [Creating type providers in each of our individual analyses?](https://docs.microsoft.com/en-us/dotnet/fsharp/tutorials/type-providers/creating-a-type-provider)
3. [TODO] Which types (name and description only) are expected to be defined? [HELP]
4. [TODO] Which top level functions (F# signature and one paragraph description) are expected to be defined?


## Module Structure

#### User OAuth GUI [Group Work]
This component performs the authentication for the user, in order to have his/her credentials to have read access to the various APIs used. This should have a `authenticate` function which either prompts the user's credentials or performs the relevant API calls to get the user's login done. The authenticated session key then needs to be passed on to the rest of the modules for them to correctly perform their API calls to fetch user data.

#### Parsing and Analysis [Individual]
Each group member is expected to write their own module, which performs individual JSON parsing of the different API endpoints, and produces analysis in a data type to be decided by each individual member. Each module is expected to have a `analysis` function, which returns an arbitrary type (defined per module), which returns some form of data structure ready to be visualised in the group front-end.

- Hardik:
- Darrick: Google
- Ethan: Spotify. Custom type provider to handle spotify data and perform analysis on it.
- Yusuf:


#### Front-end Web Application and GUI [Group]
The outputs of each individual team member's module needs to be in a format feasible for visual representation. This is highly dependent on each of the group members' individual analysis, and might be subject to change. However, a possible plan is to have each member produce a module with its own type provider for use in the main program.


## Which major "could be given to another team member to balance load" functions are there?
This isn't applicable for our project structure, as each of us is expected to deliver a module performing one branch of analysis. The remainder is all shared group work anyway.

## How will code be tested?
(e.g. which functions will be tested inputs vs outputs, is property-based testing possible)