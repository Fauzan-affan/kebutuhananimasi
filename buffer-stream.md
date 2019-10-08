To handle binary data, node provides us with the global Buffer object. Buffer instances represent memory allocated independently to that of V8's heap. There are several ways to construct a Buffer instance, and many ways you can manipulate it's data.

Pure JavaScript is Unicode friendly, but it is not so for binary data. While dealing with TCP streams or the file system, it's necessary to handle octet streams. Node provides Buffer class which provides instances to store raw data similar to an array of integers but corresponds to a raw memory allocation outside the V8 heap.

In this tutorial, we shall learn how to

Create Buffer
Write data to Buffer
Read the data from Buffer.

We can think of the whole stream and buffer process as a bus station. In some bus stations, a bus is not allowed to depart until a certain amount of passengers arrive or until a specific departure time. Also, the passengers may arrive at different times with different speed. Neither the passengers nor the bus station has control over passengers’ arrival at the station.

In any case, passengers who arrive earlier will need to wait until the bus station decides to send the bus on its way. While passengers who arrive when the bus is already loading or when the bus has already departed need to wait for the next bus.

In whatever the case may be, there is always a waiting place. That is the Buffer to Node.js! Node.js can’t control the speed or time of data arrival, the speed of the stream. It only can decide when it’s time to send out the data. If it’s not yet time, Node.js will put them in the buffer — the “waiting area” — a small location in the RAM, until it’s time to send them out for processing.

A typical example where you could see buffer in action is when you’re streaming a video online. If your internet connection is fast enough, the speed of the stream will be fast enough to instantly fill up the buffer and send it out for processing, then fill another one, and send it out, then another, and yet another… till the stream is finished.

But if your connection is slow, after processing the first set of data that arrived, the video player will display a loading icon, or display the text “buffering”, which means gathering more data, or waiting for more data to arrive. And when the buffer is filled up and processed, the player shows the data, the video. While playing that, more data will continue to arrive and wait in the buffer.

If the player is done processing or playing the previous data, and the buffer is not yet filled up, the text “buffering” will be displayed again, waiting to gather more data to process.

That is Buffer!

From the original definition of a buffer, it shows that while in the buffer, we can manipulate or interact with the binary data being streamed. What kind of interaction could we possibly have with this raw binary data? The Buffer implementation in Node.js provides us with a whole list of what is doable. 

