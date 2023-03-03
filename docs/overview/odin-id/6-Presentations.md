# Presentation requests and presentations

OdinID presentation request is a form in which a data consumer asks and specific user for some specific credentials, or to resolve some specific query about one or several credentials. The presentation is the aggregate of creadentials which is used as a response for that presentation request.

## Presentation request and presentation data flow
1. A data consumer creates a presentaions request for a user which asks for multiple credentials. 
2. The user accepts the request, and creates a signed presentation which enables the data consumer to access those credentials.
3. The data provider verifies those signartures, sign user's signatures and creates...
<!--- TODO -->

**IMPORTANT**: Users also have the option of rejecting the presentation request and not giving away that information. In that case flows stops in after step 1, with the user rejecting that presentation request.