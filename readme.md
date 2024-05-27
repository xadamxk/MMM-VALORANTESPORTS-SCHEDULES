# MMM-VALORANTESPORTS-SCHEDULES
An Esports schedule module for a provided Valorant tournament id.
Module for <a href="https://github.com/MichMich/MagicMirror">MagicMirror</a>.

## Previews with Configuration Samples
#### Default
<img src="https://github.com/xadamxk/MMM-VALORANTESPORTS-SCHEDULES/blob/main/screenshots/default.PNG?raw=true" title="Default Configuration Preview"  />

<details> 
  <summary>Hide Team Label Format:</summary>
  <img src="https://github.com/xadamxk/MMM-VALORANTESPORTS-SCHEDULES/blob/main/screenshots/showTeamLabelFalse.PNG?raw=true" title="Preview Hide Team Label Format"  />
	<pre><code>
config: {
	showTeamLabel: false	
}
	</code></pre>
</details>

<details> 
  <summary>Minified Format:</summary>
  <img src="https://github.com/xadamxk/MMM-VALORANTESPORTS-SCHEDULES/blob/main/screenshots/minified.PNG?raw=true" title="Preview Minified Format"  />
	<pre><code>
config: {
	showTeamLabel: false,
	showRegionAndBestOf: false,
}
	</code></pre>
</details>

<details> 
  <summary>Full Format:</summary>
  <img src="https://github.com/xadamxk/MMM-VALORANTESPORTS-SCHEDULES/blob/main/screenshots/full.PNG?raw=true" title="Preview Full Format"  />
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
|------------------------------------|---------------------|
| VALORANT Masters                   | 109940824119741550  |
| VCT Americas                       | 109974795266458277  |
| Challengers Ascension Americas     | 110502725535031835  |
| Challengers NA                     | 105555635175479654  |
| Game Changers NA                   | 106976737954740691  |
| VCT CN                             | 111691194187846945  |
| VCT EMEA                           | 106109559530232966  |
| VCT Pacific                        | 109974804058058602  |
| Challengers Ascension EMEA         | 110502729229255650  |
| Challengers Ascension Pacific      | 110502733800943900  |
| Challengers BR                     | 105555608835603034  |
| Challengers JPN                    | 105555678532655472  |
| Challengers KR                     | 105555677198805024  |
| Challengers LATAM                  | 106132846649518478  |
| Challengers LATAM N                | 105555664141146477  |
| Challengers LATAM S                | 105555666330314783  |
| Challengers APAC                   | 107910334624279390  |
| Challengers SEA ID                 | 105555627532605797  |
| Challengers SEA PH                 | 105555704030157191  |
| Challengers SEA MY & SG            | 105555705801095792  |
| Challengers SEA TH                 | 105555707205380136  |
| Challengers SEA HKG & TWN          | 105555699868690469  |
| Challengers SEA VN                 | 106470453892538426  |
| Challengers Oceania                | 107440791133814482  |
| Challengers South Asia             | 110032750555964337  |
| Game Changers SEA                  | 107115678205203231  |
| Game Changers BR                   | 106375817979489820  |
| Game Changers East Asia            | 109109622360706601  |
| Game Changers EMEA                 | 107019646737643925  |
| Game Changers JPN                  | 108752229027041361  |
| Game Changers KR                   | 109029777807406730  |
| Game Changers LATAM                | 109879575186437267  |
| Game Changers Championship         | 109222784797127274  |
| Last Chance Qualifier Americas     | 107021847879860429  |
| Last Chance Qualifier EMEA         | 107065428097668094  |
| Last Chance Qualifier Pacific      | 107022060264145155  |
| VCT LOCK//IN                       | 109551178413356399  |
| Champions                          | 107254585505459304  |
| Challengers Spain                  | 107566786051801019  |
| Challengers Northern Europe        | 107566795186957938  |
| Challengers DACH                   | 107566801001021372  |
| Challengers France                 | 107566807613828723  |
| Challengers East                   | 107566814199410292  |
| Challengers Türkiye                | 107566833830494141  |
| Regional League CIS: Milestone     | 107566843942399607  |
| Challengers MENA                   | 108001668454736456  |
| Challengers Italy                  | 109551156421687480  |
| Challengers Portugal               | 109551158912464238  |
