---
layout: default
post_list: false
toc: false
comment: false
home_btn: true
btn_text: true
footer: true
highlight: false
permalink: /
---

# TOWER OF BABEL FOR THE IGNORANT

<br>

`For me, being interested or not surpasses all else, and constructs my entire existence.`

`(๑•̀ㅂ•́)و✧ 感不感兴趣对我来说比什么都重要，可以说是我人生的全部。`

## Quick Access

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

**Knowing yourself is the beginning of all wisdom.**
  - Aristotle

**“We should consider every day lost on which we have not danced at least once.“**
  - Friedrich Wilhelm Nietzsche
