# Tutorial WebServer

## Commit 1 Reflection

in the first line `handle_connection` function handles a TCP stream for sending and receiving data. 

The second line creates a buffered reader, `buf_reader`, from the TCP stream. The `BufReader` struct in Rust is used to add buffering to Read instances. the first method `lines()` returns an iterator over the lines of the buffer. the second method `map(|result| result.unwrap())` applies a function to each item yielded by the iterator The function provided here, `|result| result.unwrap()`, takes a Result and calls the `unwrap` method on it. The `unwrap` method returns the String if the result is Ok, or panics if the result is Err. the third method `take_while(|line| !line.is_empty())` continues to take items from the iterator as long as the provided condition is true. The condition here, `|line| !line.is_empty()`, checks that each line is not empty. As soon as an empty line is encountered, the iterator stops. the last method `collect` consumes the iterator and collects the items into a collection. In this case, the items are collected into a Vec<String>, which is a vector of strings.

Finally, the function prints the `http_request` vector to the console with the `println!` macro. The `{:?}` format specifier is used to print the vector in debug format, and the `#` modifier is used to pretty-print the output, with each item on a new line.

## Commit 2 Reflection

![commit2](./image/milestone2.png)

## Commit 3 Reflection
![commit3](./image/milestone3.png)

## Commit 4 Reflection
`/sleep` is slow because we set the sleep time to 10 seconds. The server will wait for 10 seconds before sending the response back to the client.

## Commit 5 Reflection
The ThreadPool works by creating a vector of workers. Each worker is a thread that waits for a job to execute. The worker will execute the job when it is available. The worker will continue to execute jobs until the server is shut down. The ThreadPool is responsible for managing the workers and sending jobs to them. The ThreadPool will create a new worker when it is initialized and will send jobs to the workers when they are available.
