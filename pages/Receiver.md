{{ infobox_object({
	"id": 123,
	"name": "Receiver",
	"category": "Electronics",
	"sublayer_width": 15
}) }}

Listens for a signal on the given frequency.

The receiver will differentiate between broadcast signals and transmitter signals, and prefer transmitter signals. That means if a broadcaster is broadcasting a value of 0.5 over the receivers frequency, and a transmitter is transmitting the value 1.0, the receiver will receive 1.0.
