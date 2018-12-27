---
layout: post
title:  "All I Want for Christmas is Generic Associated Types in Rust"
date:   2018-12-26 09:13:20 +0100
categories: jekyll update
---
For next Christmas, I would like Santa to come down the chimney with Generic Associated Types (GAT) for Rust. The reason why is to create streaming iterators - iterators that shares a reference to its invariant while iterating. 

One of my use-cases for streaming iterators is to create efficient page reading of large data files. It would be great if I could create a page iterator that allocated  a byte buffer to read in disk pages and borrows its page buffer when it is iterated - taken advantage of Rust's rich ecosystem of iterators. 

There are workarounds but it's not as clean as if Generic Associated Types were supported.

{% highlight rust %}
let file = File::open("large_file.dat")?;
for page in file.pages() {
    // do something with each disk page
}
{% endhighlight %}

In this code example, a puge buffer is borrowed as `page` with type `&[u8]` and is encapsulated within the page iterator. This would allow to create high-level, efficient abstractions of reading pages from a disk.
