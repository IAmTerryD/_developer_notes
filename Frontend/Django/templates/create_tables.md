```
{% extends "main.html" %}
{% block content %}
    <h1 class="display-6">Patients</h1>
    <table class="table">
        <thead>
            <tr>
                <th scope="col">Last</th>
                <th scope="col">First</th>
                <th scope="col">Date of Birth</th>
            </tr>
        </thead>
        <tbody>
            {% for patient in instances %}
                <tr>
                    <td>{{ patient.last_name }}</td>
                    <td>{{ patient.first_name }}</td>
                    <td>{{ patient.date_of_birth }}</td>
                </tr>
            {% endfor %}
        </tbody>
    </table>
{% endblock content %}

```