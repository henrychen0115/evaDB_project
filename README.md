# EvaDB Project: Restaurant Recommendation System

## Introduction:
In today's fast-paced world, people often find it challenging to make quick decisions on where to eat. People like me waste time every day deciding what to eat or going back and forth with a friend trying to have each other decide upon a location. Our solution? The Restaurant Recommendation System. By integrating advanced algorithms with the Google Maps API, this system offers tailored restaurant suggestions based on the user's location and preferences, thereby elevating the dining experience.

## Description:
The Restaurant Recommendation System first pinpoints the user's location and then enumerates nearby restaurants. Its unique proposition is its ability to personalize these suggestions based on various user preferences archived in our database. This includes preferences like cuisine type, dietary needs, current cravings, and budget. This not only streamlines the decision-making process but also promises an enhanced dining experience by syncing with the user's precise requirements.

## Methodology:

### Location Retrieval:
- Harnesses the Google Maps address search API to transform an input address into precise latitude and longitude.
- This data is then employed to fetch proximate restaurants within a user-defined radius via the Google Maps places API. The input can be a general address, with the API ensuring its conversion into an exact location. Users can also dictate the radius for their restaurant search, quantified in meters.

### Data Collection:
- Restaurant specifics such as name and price category are sourced from the Google Maps API.
- User preference data, encompassing facets like cuisine, dietary restrictions, and pricing, are cataloged in a local PostgreSQL database. EvaDB serves as the intermediary for querying this data.

### User Preference Matching:
- The system filters restaurants in tandem with the user's saved preferences, considering aspects like dietary choices, favored cuisines, and more. This structure also facilitates easy expansion, with the addition of new user preference columns in the database as required.
- The system taps into OpenAI's ChatGPT for nuanced, real-time recommendations, bolstering its accuracy through conversational AI.

### Recommendation Generation:
- Users are presented with restaurant suggestions that not only are in proximity but also align seamlessly with their specified preferences.

### Integration with ChatGPT:
- The project integrates OpenAI's ChatGPT to refine restaurant recommendations. By leveraging conversational AI, the system can balance nearby restaurant data with stored user preferences, delivering the most apt dining suggestions.

### Integration with EvaDB:
- Throughout the development phase, EvaDB was employed as a middleware to retrieve data from the local PostgreSQL database. This system benefitted from EvaDB's ability to process each database row (representing individual users) using ChatGPT's built-in functions.

## Difficulties and Issues:
- A key challenge was the lack of extensive documentation for EvaDB's custom functions, leading to trial-and-error-based progress. The project also grappled with unsupported data types in EvaDB, such as array types and UUID, necessitating workarounds.
- The limited restaurant data fetched from Google Maps was another hurdle, emphasizing the need for more detailed restaurant categorizations in the returned list.

## Future Endeavors:
- Expanding the data set by incorporating other APIs besides Google Maps.
- Envisioning a user interface where users can log in, input preferences, set their location, and specify restaurant search radii. This would eliminate the current manual data input system.
- Enhancing the user experience by displaying pertinent restaurant details, like Google Maps locations and ratings.
- Recording previously suggested restaurants for users and adding time-based preferences for meal-specific recommendations.

## Conclusion:
The Restaurant Recommendation System epitomizes the synergy of cutting-edge APIs with intricate algorithms to curate user-centric experiences. With this tool, indecisive diners no longer have to wade through endless options or make uninformed decisions. Instead, they receive curated suggestions aligned with their tastes, translating to memorable dining experiences. The sole recommendation approach, as opposed to multiple suggestions, is designed for those who struggle with choices, offering them a clear direction for their next meal. Looking forward, real-time feedback loops could further refine the system, allowing it to evolve based on user reviews and ratings.
