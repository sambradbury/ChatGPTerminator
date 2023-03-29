 TODO:
 Overall, the code looks clean and well-structured with good use of classes and
 functions. However, there are various ways to enhance its efficiency. Here are
 some suggestions:
  1 Use a more efficient data structure: The current implementation uses a list
    to store the conversation history. This can lead to slower performance with
    larger amounts of data. Consider using a more efficient data structure, such
    as a deque or a database, that is optimized for appending and quickly
    accessing the most recent messages.
  2 Lazy loading of configuration: The loadConfig() method is called within the
    run() method every time the program is run, even though the configuration
    only needs to be loaded once. Consider lazy loading the configuration on the
    first run and storing it for subsequent runs.
  3 Avoid redundant API requests: The getResponse() method makes an API request
    for every user prompt, even if the previous prompt has not changed. Consider
    caching the response for a prompt if it has not changed since the previous
    request.
  4 Optimize saving chat history: The saveChat() method writes the chat history
    to a file every time it's called. This can be inefficient when saving
    frequently. Consider buffering the chat history in memory and writing it to
    the file in batches to avoid I/O overhead.
  5 Use a more performant text editor library: The code currently uses the
    prompt_toolkit library, which is great for its rich features, but can be
    slower with large amounts of data. Consider using a lighter text editor
    library, such as curses, for faster performance.
  6 Avoid excessive console printing: The code makes frequent use of console
    prints, which can be slow and inefficient. Consider consolidating multiple
    print statements into one, or using a logger library to better manage output.
  7 Use asynchronous programming: The code is currently running on a single
    thread, which can slow down performance. Consider using asynchronous
    programming with Python's asyncio library to handle multiple requests
    simultaneously and reduce wait time.