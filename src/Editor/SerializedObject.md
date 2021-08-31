# SerializedObject

```cs
using UnityEngine;
using UnityEditor;

[CustomEditor (typeof(Character))]
public class CharacterInspector : Editor
{
    SerializedProperty hpProperty;

    void OnEnable ()
    {
        hpProperty = serializedObject.FindProperty ("hp");
    }

    public override void OnInspectorGUI ()
    {
        serializedObject.Update ();

        EditorGUILayout.IntSlider (hpProperty, 0, 100);

        serializedObject.ApplyModifiedProperties ();
    }
}
```
