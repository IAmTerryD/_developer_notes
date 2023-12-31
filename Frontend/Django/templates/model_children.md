# set_all

Returns all instance of a particular child in a model (parent).

```
      {% for skill in profile.skill_set.all %}
      <span class="btn btn-primary btn-small"> {{ skill }} </span>
      {% endfor %}
```
