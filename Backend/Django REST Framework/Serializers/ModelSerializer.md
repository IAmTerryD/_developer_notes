```
# app > serializers.py

from rest_framework.serializers import ModelSerializer
from .models import Note

class NoteSerializer(ModelSerializer):
    class Meta:
        model = Note
        fields = '__all__'
        # fields = ['body','updated'] for indivial fields
```

```
# app > views.py 

@api_view(['GET'])
def get_notes(request):
    notes = Note.objects.all()
    # Need to serialize notes
    # many = serializing multiple objects
    serializer = NoteSerializer(notes, many=True)
    return Response(serializer.data)
```
