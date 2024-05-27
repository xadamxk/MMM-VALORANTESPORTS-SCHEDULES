# MMM-VALORANTESPORTS-SCHEDULES
An Esports schedule module for a provided Valorant tournament id.
Module for <a href="https://github.com/MichMich/MagicMirror">MagicMirror</a>.

## Previews with Configuration Samples
#### Default
<img src="https://github.com/xadamxk/MMM-VALORANTESPORTS-SCHEDULES/blob/main/screenshots/default.png?raw=true" title="Default Configuration Preview"  />

<details> 
  <summary>Hide Team Label Format:</summary>
  <img src="https://github.com/xadamxk/MMM-VALORANTESPORTS-SCHEDULES/blob/main/screenshots/showTeamLabelFalse.png?raw=true" title="Preview Hide Team Label Format"  />
	<pre><code>
config: {
	showTeamLabel: false	
}
	</code></pre>
</details>

<details> 
  <summary>Minified Format:</summary>
  <img src="https://github.com/xadamxk/MMM-VALORANTESPORTS-SCHEDULES/blob/main/screenshots/minified.png?raw=true" title="Preview Minified Format"  />
	<pre><code>
config: {
	showTeamLabel: false,
	showRegionAndBestOf: false,
}
	</code></pre>
</details>

<details> 
  <summary>Full Format:</summary>
  <img src="https://github.com/xadamxk/MMM-VALORANTESPORTS-SCHEDULES/blob/main/screenshots/full.png?raw=true" title="Preview Full Format"  />
	<pre><code>
config: {
	showPeriodLabel: false,
	use24HourTime: true,
	useTeamFullName: true,
	showTournamentBlock: true
}
	</code></pre>
</details>

## Installation
In your terminal, go to your MagicMirror's Module folder:
````
cd ~/MagicMirror/modules
````

Clone this repository:
````
SSH: git clone git@github.com:xadamxk/MMM-VALORANTESPORTS-SCHEDULES.git
HTTPS: git clone https://github.com/xadamxk/MMM-VALORANTESPORTS-SCHEDULES.git
````

Install/Update Dependencies:
````
npm install
````

## Configuration
Add `MMM-VALORANTESPORTS-SCHEDULES` module to the `modules` array in the `config/config.js` file:
````javascript
modules: [
	{
		module: "MMM-VALORANTESPORTS-SCHEDULES",
		position: "bottom_left",
		config: {}
	}
]
````
### Configuration Options

| **Option** | **Type** | **Default** | **Description** |
| --- | --- | --- | --- |
| `updateInterval` | integer | 60 | Number of minutes to poll api for updates. |
| `apiKey` | string | '0TvQnueqKa5mxJntVWt0w4LpLfEkrV1Ta8rQBb9Z' | Api key used to query esports API - all users' api key is the default key. |
| `leagueIds` | array | [""] | Array of league ids to get esport standings. Currently the API only supports a single league id. If no id is provided, then all region games will be provided. Refer to league table below for ids of other leagues. Defaults to TBD.|
| `hl` | string | 'en-US' | Host language/ locale to use when requesting esports data. |
| `numberOfFutureGames` | integer | `5` | Number of future games to display. |
| `use24HourTime` | boolean | false | Use 24 hour format (hh:mm) rather than 12 hour format (hh PERIOD) |
| `useTeamFullName` | boolean | false | Show teams' full name rather than teams' code. |
| `showPeriodLabel` | boolean | true | Show period (AM/PM) after time. |
| `showTeamLabel` | boolean | true | Show team label (name/code). Use `false` for slim component. |
| `showRegionAndBestOf` | boolean | true | Show region and best of format for games. |
| `showTournamentBlock` | boolean | false | Show tournament block (ie. Playoffs - Round 1) after start date.|

### League Ids
League Ids are obtained via the following CURL:
```
curl --location 'https://esports-api.service.valorantesports.com/persisted/val/getLeagues?hl=en-US&sport=val' \
--header 'x-api-key: 0TvQnueqKa5mxJntVWt0w4LpLfEkrV1Ta8rQBb9Z'
```

| **League** | **League Id** |
| --- | --- |

