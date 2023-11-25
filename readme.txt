This is an example project that shows how to send and receive messages from the arcane mirage pixel streaming player.

On the GameMode Blueprint you will find the logic that makes the mobile controls turn off or on depending on what you receive from the pixel streaming player when you send the message "GetDevice".

Using "Send Pixel Streaming Response" with the descriptor "GetDevice" will make the pixel streaming player to send an On Input event that contains a JSON:
{
	event: 'DeviceDescription',
	data: {
        	mobile: bool          
              }
}

Which will show true or false on the mobile field depending if your experience is running on a desktop or mobile browser. Keep in mind this example only runs it at startup.

When the pixel streaming player sends an event, you need to bind the On Input Event from the pixel streaming input component. Then you will process the descriptor as you would normally process a JSON.

Remember:
-Add the PixelStreamingInput component to the BP that will send and receive messages from the pixel streaming player
-Add the plugin JSON Blueprint Utilites from Epic to be able to better parse JSONs.