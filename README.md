## Disclaimer
The following two points were originally in the (outdated) team coursework spec and we feel they are the only two we have not fully answered (mostly to do with types). Reason being that we weren't sure that they completely applied to our custom project, given the parallel nature of our work that does not (in the individual work stage) require any interoperability or dependencies. As such, we have done our best to answer them descriptively, but it is extremely difficult to specify types at this juncture and thus they may not be explicit at this stage.

1. [TODO] Which types (name and description only) are expected to be defined?
2. [TODO] Which top level functions (F# signature and one paragraph description) are expected to be defined?

## What is the expected Team deliverable?
Four separate analyses of user data from Google / Spotify / Facebook APIs, visualised on a web-application written in FABLE(?)

Extension: Combination of our analyses to derive even more meaningful inferences.

Resources:
- [Google APIs](https://developers.google.com/apis-explorer)
- [Spotify APIs](https://developer.spotify.com/documentation/web-api/reference/users-profile/get-users-profile/)

## Questions (TO-DO)
1. [TC] We intend to use the type providers in FSharp.Data for parsing of JSON. Allowed?
2. [TC] [Creating type providers in each of our individual analyses?](https://docs.microsoft.com/en-us/dotnet/fsharp/tutorials/type-providers/creating-a-type-provider)
3. [TC] Nuget packages for HTTP requests, etc?

## Module Structure

#### User OAuth GUI [Group]
This component performs the authentication for the user, in order to have his/her credentials to have read access to the various APIs used. This should have a `authenticate` function which either prompts the user's credentials or performs the relevant API calls to get the user's login done. The authenticated session key / access token then needs to be passed on to the rest of the modules for them to correctly perform their API calls to fetch user data. A custom type needs to be made to encapsulate this information and pass it to the 4 parallel analysis modules.

#### Parsing and Analysis [Individual]
Each group member is expected to write 2 of their own modules:
- The main module, which performs individual JSON parsing of the different API endpoints, and produces analysis in a data type to be decided by each individual member. This is expected to have an `analyse` function to be called from top level, which returns an arbitrary type (defined per module), which returns some form of data structure ready to be visualised in the group front-end.
- A second module containing an `Expecto` test suite and any relevant test interfaces required, depending on individual implementation. An example of this would be to encapsulate all tests in a `testModule` function. This separates the tests from the shipped product and keeps code cleaner.

The following contains a rough idea of the analyses we wish to perform. However, these may have to change as we get more familiar with the APIs.
- Hardik: Facebook
- Darrick: Google - Calendar
- Ethan: Spotify
- Yusuf: Heatmap of music listening patterns


#### Front-end Web Application and GUI [Group]
The outputs of each individual team member's module needs to be in a format feasible for visual representation. This is highly dependent on each of the group members' individual analysis, and might be subject to change. The intention for now is to use javascript charting libraries on npm to produce different varieties of graphics (heatmaps, graphs, connected node maps, etc.) These will be worked out later.


## Which major "could be given to another team member to balance load" functions are there?
This isn't applicable for our project structure, as each of us is expected to deliver a module performing one branch of analysis. The remainder is all shared group work anyway.

## How will code be tested?
Each member would be expected to test their models on a stub data set that we synthesize. Where property-based testing can be done, we intend to make unit tests for individual functions. For example, if we have to write our own JSON parser, we would be able to declare certain properties we desire and make sure it works. However, in the event of the output of the final analysis, this is more difficult.
