<script>
let location = "";
let temparature = "";
let description = "";
async function getWeather() {
  fetch('https://goweather.herokuapp.com/weather/' + location)
	.then((response) => response.json())
	.then((data) => {
  	//Able to change whatever name you like Example: weatherTemparature = data.temperature the name of data should not be changed.
       temperature = data.temperature; // Path for temperature
  	description = data.description; // Path for description
	});
}
    </script>

<h1>Weather App</h1>

<form on:submit|preventDefault={getWeather}>    
    <label for="location">Location:</label>
    <input id="location" bind:value={location} type="text" />
    <button type="submit">Check</button>
</form>
<p>Temperature: {temperature}</p>
<p>Description: {description}</p>
