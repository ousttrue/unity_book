# Layout


```cs
var r = GUILayoutUtility.GetRect(GUIContent.none, GUIStyle.none, GUILayout.Height(EditorGUIUtility.singleLineHeight * 3 + 20));
```

```cs
Rect r = EditorGUILayout.GetControlRect ();
```

## begin/end

```cs
using (new GUILayout.VerticalScope(GUI.skin.box))
{
    GUILayout.Button("Click me");
    GUILayout.Button("Or me");
} 
```

```cs
GUILayout.BeginArea(new Rect(16,16,300,300));
GUILayout.Label(title, guiSkin.label);
GUILayout.Label ("Time : "+lapseTime.ToString("0.0"), guiSkin.label);
GUILayout.HorizontalSlider(70,0,100);
GUILayout.Button ("Click!", guiSkin.button);
GUILayout.EndArea();
```

```cs
EditorGUILayout.BeginHorizontal();
chara.hp        = EditorGUILayout.IntField( chara.hp, GUILayout.Width(48) );
chara.maxHp     = EditorGUILayout.IntField( chara.maxHp, GUILayout.Width(48) );
EditorGUILayout.EndHorizontal();
```
