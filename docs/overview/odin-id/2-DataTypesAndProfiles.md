# Data types and profiles

## Data types

OdinID differentiates between to types of data, static and dynamic:
- **Static**: Refers to data values that normally doesn't change over time. Native language and birth date for example are data fields which won't change over time.
- **Dynamic**: Data values that change over time, for example, interests shopping activity, workout preferences, etc.

This data differentiation allows OdinID to create different user profiles for dapps to fulfill with static or dynamic data.

## Profiles

The identity system has 4 different profiles which can be divided in two. One Core profile with only static data and 3 behaviour profiles retaled to specific topics, currentyly supporting shopping, gaming and sports. More behaviour profiles will be added in the future.

- **Core profile**: Only contains static data which can be compared easily and can be easily ranked by the trust system. This data is the core of the user identity and is the most basic profile.
- **Shopping profile**: Realated to user shopping behaviour filled mainly with dynamic data related like shopping frequence, reviews, product cateregories, etc. This profile is great for data consumers to be able to create more adequate offers to their costumers and understand their needs.
- **Gaming profile**: Filled with gaming behaviour (platforms, favourite genres, achivements, play time, etc.) data making the user able to connect to new games and platforms in seconds, share gaming achievements, get early access to new games and much more.
- **Sports profile**: More focused on user sport activity. Workout preferences, favourite sports, workout sessions, etc. create a profile which will let users access to better deals on sport products or services.

The trust algorithm will use mainly core profile data to create its rates, but behaviour profiles and its size will also affect to the trust rate of a user. A user with a more complete profile is likely to have a high trust rate.