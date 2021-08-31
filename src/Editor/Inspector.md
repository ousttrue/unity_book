# Inspector

## CustomEditor

```cs
using UnityEngine;
using UnityEditor;

[CustomEditor (typeof(Character))]
public class CharacterInspector : Editor
{
    Character character = null;

    void OnEnable ()
    {
        //Character コンポーネントを取得
        character = (Character) target;
    }

    public override void OnInspectorGUI ()
    {
        base.OnInspectorGUI ();

        //攻撃力の数値をラベルとして表示する
        EditorGUILayout.LabelField ("攻撃力", character.攻撃力.ToString ());
    }
}
```

## text

```cs
public override bool HasPreviewGUI()
{
    return true;
    //return Application.isPlaying;
}

public override GUIContent GetPreviewTitle()
{
    return new GUIContent("Title");
}

public override string GetInfoString()
{
    return "Status";
}
```

## sample

```cs
public override bool HasPreviewGUI()
{
    return Application.isPlaying; // Editor時だと表示が乱れる？
}

public override GUIContent GetPreviewTitle ()
{
    return new GUIContent ("プレビュー名");
}

public override void OnPreviewSettings ()
{
    GUIStyle preLabel = new GUIStyle ("preLabel");
    GUIStyle preButton = new GUIStyle ("preButton");

    GUILayout.Label ("ラベル", preLabel);
    GUILayout.Button ("ボタン", preButton);
}

public override void OnPreviewGUI (Rect r, GUIStyle background)
{
    GUI.Box (r, "Preview");
}
```
