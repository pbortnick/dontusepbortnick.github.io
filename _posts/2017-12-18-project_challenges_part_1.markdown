---
layout: post
title:      "Project Challenges: Part 1"
date:       2017-12-18 18:25:08 +0000
permalink:  project_challenges_part_1
---


For my personal coding project that I described 2 blog posts ago, I decided to implement a show more / show less function for post descriptions. I remembered reviewing this type of function within my Flatiron studies. So I consulted the section and although it helped guide with the "show more" function, it didn't include "show less". This is a fairly common practice on sites so I figured there would be a lot of helpful information and sample code out there. There is, but since I am constructing this project from scratch, the information didn't quite fit my needs.

Thankfully, my Flatiron education taught me how to LEARN. So...I did it myself.

This is what I finally came up with and it is working!

```
  $(function() {
	
    $(".more").on('click', function() {
      if ($(this).text() == "View Less") {
        $(this).text("View More");
      } else {
        $(this).text("View Less");
      };
			
      var id = $(this).data("id");
			
      if ($(this).text() == "View More") {
        $.get("/posts/" + id + "/body", function(data) {
          // Replace text of body-id div
          $("#body-" + id).text(data);
        });
      } else {
        $.get("/posts/" + id + "/body", function(data) {
          $("#body-" + id).text(data.substring(0,27));
					
        });
      };
    });
  });
```

In the first part of the function, the button (with class "more") will change its display text from "View More" to "View Less" & vice versa once clicked. According to what the button says, the body of the text will either be truncated or fully displayed upon clicking the button.
