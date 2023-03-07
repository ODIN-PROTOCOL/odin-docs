# Trust Algorithm

TrustMesh's trust algorithm rates users, data providers and credentials for it to be more secure and to handle legit verifiable information.

The algorithm takes into account all the static data as a core reference. This means that new profiles will need to fullfill some static fields first to be able to get a initial trust rating.

The trust rating compares values of same fields given by different data providers from the ecosystem to search for non-coherent data. Let see a simplified example: 

Data providers A, B, C, D, E and F offered user Bob the same credential, "Native language". While providers A, B, C, D and E offered value "English", provider F claimed that users "Native language" is "French". Based on probability provider F has claimed a wrong value for that credential, this means the F provider's trust is going to decrease slightly. The more statistically failed credentials F provider issues the lower the trust will get even slashing their data providers stake funds.
