# Trust Algorithm

OdinID's trust algorithm rates the users, data providers and credentials trust, for the whole system to be more secure and to handle legit verifiable information.

The algorithm takes into account all the static data as a core reference. This means that all new identities need to fullfill this static fields first to be able to get a basic trust rating.

The trust rating compares value of same fields given by different data providers from the ecosystem to search for non-coherent values. Let see a simplified example example: Data provider A, B, C, D, E and F offered user Bob the same credential, "Native language". While providers A, B, C, D and E offered value "English", provider F claimed that users "Native language" is "French". Based on probability provider F has claimed the wrong value for that credential, this means the F provider's trust is going to decrease slightly. The more statistically failed credentials F provider issues the lower the trust will get even slashing their data providers stake funds.
