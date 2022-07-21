# JavaScript 30 #21: speedometer-and-compass
This project uses Geolocation API to get users' location information. </br>
### General Info
navigator.geolocation.watchPosition() takes a callback function with the parameter of the current location data of the user, being called automatically each time the position of the device changes.
```
navigator.geolocation.watchPosition(data => {
      console.log(data); // location data
    }, (err) => {
      console.err(err);
      alert('Something went wrong!');
    })
```
This data contains speed and heading properties <br>
```
data.coords.speed   // represens the velocity of the device in meters per second
data.coords.heading // represents the direction in which the device is traveling
```
Finally, we change the text content of the speedValue and css property of the arrow element with those values 
```
speedValue.textContent = data.coords.speed;
arrow.style.transform = `rotate(${data.coords.heading}deg)`;
```
**Note that these features are only available in secure contexts (HTTPS) and most accurate for devices with GPS**
