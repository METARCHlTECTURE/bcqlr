---
layout: default
post_list: false
toc: false
comment: false
home_btn: true
btn_text: true
footer: true
highlight: false
permalink: /hl
---

# HIGHLIGHTED

<tr>
    <td>
        <ul>
            {% if site.collection_order %}
                {% for col_in_order in site.collection_order %}
                    {% for collection in site.collections %}
                        {% if collection.label == col_in_order %}
                            {% for post in collection.docs %}
                                {% if post.publish != false %}
                                   {% if post.highlight == true %}
                                    <li>
                                        <a class="a_title" href="{{site.url}}{{site.baseurl}}{{post.url}}">{{post.title}}</a>
                                    </li>
                                    {% endif %}
                                {% endif %}
                            {% endfor %}
                        {% endif %}
                    {% endfor %}
                {% endfor %}
            {% else %}
                {% for collection in site.collections %}
                    <p class="h_collection_label">
                        {% if collection.alias %}
                            {{collection.alias}}
                        {% else %}
                            {{collection.label}}
                        {% endif %}
                    </p>
                    {% for post in collection.docs %}
                        {% if post.publish != false %}
                            <li>
                                <a class="a_title" href="{{site.url}}{{site.baseurl}}{{post.url}}">{{post.title}}</a>
                            </li>
                        {% endif %}
                    {% endfor %}
                {% endfor %}
            {% endif %}
        </ul>
    </td>
</tr>