# Report

## The MUD generator

The MUD generator is a custom integration for Home Assistant that is able to create and expose a unique MUD file.

When the user presses the button located in the Home Assistant home page, the process starts.

The first operation that the integration does is to load the original mud draft (**mud_draft.json**), that is the MUD file related to Home Assistant and generated automatically by the integration itself.

Then, it verifies the presence of MUD snippets in two different locations: the first is _/config/custom_components_, where we can create and add a personalized integration, and the second is the reference in the files named **manifest.json** of every default installed integration.

After completing the task, it adds the new policies and the new access lists to the final file and it exposes the file itself.

In _/config/www/MUD_ we can find the generated MUD snippet, that has the following structure: at the beginning there are some common parameters like _mud-version_, _cache-validity_, _is-supported_, _systeminfo_, _mfg-name_, _documentation_ and _model-name_. Then there are the names of the various _access-list_, both in one direction and the other. In the final part, we can read the specifications of these access lists and the relative Access Control Entries with their endpoints.

## The integrations

In this repository you can find three MUD files of three different integrations for Home Assistant: Spotify, CO2 Signal and easyEnergy. The endpoints present in the snippets are all retrieved from the documentation and from the source code of the three components.

With the Spotify integration you can remotely control the music playback and it talks with _api.spotify.com_, _open.spotify.com_ and _accounts.spotify.com_.

CO2 Signal "gives you access to where the electricity in a specific region comes from, how it was produced and how much carbon was emitted to produce it" (https://www.co2signal.com) and talks with _co2signal.com_ and _electricitymap.org_.

Instead, with easyEnergy you can check and monitor the prices of energy and gas and it talks with _easyenergy.com_.
