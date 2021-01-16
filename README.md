Tag is simple and flexible binary data format inspired from Minecraft's Tag format.
I created it for my personal unity projects to save game, level, settings etc and network communication.
Take care i did not test it enough!

SUPPORTED DATA TYPES

    bool, byte, int, float, string, Vector2, Vector3, Vector4, Quaternion, Color,
    bool[], byte[], int[], float[], string[], Vector2[], Vector3[], Vector4[], Quaternion[], Color[],


CONSTRUCTOR

    var data = new Tag(
        new Tag("map", "lake"),
        new Tag("settings",
            new Tag("speed", 10),
            new Tag("time", 20),
            new Tag("private", true)
        ),
        new Tag("players",
            new Tag(
                new Tag("name", "alfantin"),
                new Tag("team", 0)
            ),
            new Tag(
                new Tag("name", "mike"),
                new Tag("team", 1)
            )
        ),
        new Tag("teams",
            Color.red,
            Color.blue
        )
    );

TO SAVE & LOAD

    data.Save("test.Tag");
data = Tag.Read("test.Tag");
    
TO SET

    data.Set("name", value);
    
TO GET

    data.GetBool("name");
    data.GetByte("name");
    data.GetInt("name");
    data.GetFloat("name");
    data.GetString("name");
    data.GetVector2("name");
    data.GetVector3("name");
    data.GetQuaternion("name");
    data.GetColor("name");
    data.GetTag("name");
    data.GetBoolArray("name");
    data.GetByteArray("name");
    data.GetIntArray("name");
    data.GetFloatArray("name");
    data.GetStringArray("name");
    data.GetVector2Array("name");
    data.GetVector3Array("name");
    data.GetQuaternionArray("name");
    data.GetColorArray("name");
    data.GetTagArray("name");
    
    //EXAMPLE
    data.GetTagArray("players")[0].GetString("name");


