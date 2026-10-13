docker build -t feedback-node .
docker build --load -t feedback-node .
docker run -p 3000:80 --name feedback-app --rm -d feedback-node

http://localhost:3000/
add a title and document text like:
Title - awesome
Document Text - This is my first feedback

http://localhost:3000/feedback/awesome.txt -> this will show the following text:
This is my first feedback

But all this will be lost when the container is stopped because this data is currently only stored in the container and not on the local host.