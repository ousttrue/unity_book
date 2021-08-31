# Asset

```cs
AssetDatabase.StartAssetEditing ();
foreach (var sound in sounds) {     
    var path = AssetDatabase.GetAssetPath (sound);     
    var audioImporter = AudioImporter.GetAtPath (path) as AudioImporter;     
    if (audioImporter){     
        audioImporter.threeD = false;    
        //AssetDatabase.ImportAsset(path);
        EditorUtility.SetDirty(sound);
    }
}
AssetDatabase.StopAssetEditing ();

// import dirty objects 
AssetDatabase.Refresh();
```
