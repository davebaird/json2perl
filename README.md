

    $ alias json2perl='docker run --rm -i --user "$(id -u):$(id -g)" --volume "$PWD:/workdir" dvz5/json2perl'

    $ xml.feed.reader https://news.yale.edu/topics/science-technology/rss \
        | catmandu convert XML to JSON \
        | jq '[.[0].entry[]]' \
        | json2perl \
        | hicat