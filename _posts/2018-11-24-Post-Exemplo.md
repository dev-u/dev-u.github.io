---
title: "Post Exemplo: Como utilizar a notação Markdown!"
date: 2018-11-24
tags: [dev-u, jekyll, markdown, tutorial]
header:
    image: "/images/devu_banner.jpg"
excerpt: "Dev-U, Jekyll, Markdown, Tutorial"
---

# H1 Heading

## H2 Heading

### H3 Heading

Here's some basic text.

And here's some *italics*

Here'1s some **bold** text.

What about a [link](https://github.com/HugoUchoasBorges)?

Here's a bulleted list:
* First item
+ Second item
- Third item

Here's a numbered list:
1. First
2. Second
3. Third

Python code block:
```python
    import numpy as np
    def test_function(x, y):
        z = np.sum(x,y)
        return z
```

R code block:
```r
library(tidyverse)
df <- read_csv("some_file.csv")
head(df)
```

Here's some inline code `x+y`.

Here's an image:
<img src="{{ site.url }}{{ site.baseurl }}/images/tutorial/celeste.jpg" alt="linearly separable data">

Here's another image using Kramdown:
![alt]({{ site.url }}{{ site.baseurl }}/images/tutorial/smb.jpg)

