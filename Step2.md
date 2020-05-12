


# Display EV Charging Stations using Places REST API
Add the following code before </script> tag
```javascript
            function displayEV(){
                 var evIcon = new H.map.Icon('img/EV.png');
                var geocoder = platform.getSearchService();
                let geocoderParams = {
                    at : markerPosition.lat + ',' + markerPosition.lng,
                    categories: '700-7600-0322'
                }

                function onResult(result){
                        console.log(result);
                        if(result.items){

                            result.items.forEach(item => {
                                let evMarker = new H.map.Marker(item.position,{ icon: evIcon }); 
                                map.addObject(evMarker);
                            });
                        }
                }
                
                geocoder.browse(geocoderParams,onResult,alert);
            }

            displayEV();
```
</br> Double-click on saved file to view on browser

[![Foo](https://github.com/kuberaspeaking/HERE-JS-workshop/blob/master/img/s3.png)](https://github.com/kuberaspeaking/HERE-JS-workshop/blob/master/Step3.md) 

