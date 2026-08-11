---
layout: page
permalink: /blog/
title: Blog
description:
nav: true
nav_order: 4
---

<html>
<head>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Roboto+Serif:ital,opsz,wght@0,8..144,100..900;1,8..144,100..900&display=swap" rel="stylesheet">

    <style>
        body {
            font-family: "Roboto Serif", serif;
            font-optical-sizing: auto;
            font-weight: 200;
            font-size: 0.96rem;
        }

        strong, b {
            font-weight: 550;
        }

        h1, h2, h3, h4, h5, h6 {
            font-weight: 350;
        }

        .blog-list {
            margin-top: 2.5rem;
        }

        .blog-post {
            display: block;
            padding: 1.5rem 0;
            border-top: 1px solid rgba(128, 128, 128, 0.25);
            text-decoration: none;
            color: inherit;
            transition: opacity 0.2s ease;
        }

        .blog-post:last-child {
            border-bottom: 1px solid rgba(128, 128, 128, 0.25);
        }

        .blog-post:hover {
            opacity: 0.65;
        }

        .blog-post-title {
            margin: 0 0 0.45rem 0;
            font-size: 1.25rem;
            font-weight: 400;
        }

        .blog-post-meta {
            display: flex;
            gap: 0.8rem;
            color: #777;
            font-size: 0.82rem;
        }

        .blog-post-author::after {
            content: "·";
            margin-left: 0.8rem;
        }

        .blog-empty {
            color: #777;
            padding: 2rem 0;
        }
    </style>
</head>
</html>

<div class="blog-list">
    {% if site.posts.size > 0 %}

        {% for post in site.posts %}
            <a class="blog-post" href="{{ post.url | relative_url }}">

                <h2 class="blog-post-title">
                    {{ post.title }}
                </h2>

                <div class="blog-post-meta">
                    {% if post.author %}
                        <span class="blog-post-author">
                            {{ post.author }}
                        </span>
                    {% endif %}

                    <span>
                        {{ post.date | date: "%b. %d, %Y" }}
                    </span>
                </div>

            </a>
        {% endfor %}

    {% else %}

        <p class="blog-empty">
            No posts yet.
        </p>

    {% endif %}
</div>