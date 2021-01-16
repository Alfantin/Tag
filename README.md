This framework is simple and flexible binary data format inspired from Minecraft Named Binary Tag format.

I created it for my personal unity projects to save game, level, settings etc and network communication.

I did't test yet. I still developing it.

SUPPORTED TYPES

    bool, byte, int, float, string, Vector2, Vector3, Vector4, Quaternion, Color


CONSTRUCTOR

    var data = new Nbt(
        new Nbt("map", "lake"),
        new Nbt("settings", 
            new Nbt("speed", 10),
            new Nbt("time", 20),
            new Nbt("private", true)
        ),
        new Nbt("players",
            new Nbt(
                new Nbt("name", "alfantin"),
                new Nbt("team", 0)
            ),
            new Nbt(
                new Nbt("name", "mike"),
                new Nbt("team", 1)
            )
        ),
        new Nbt("teams", 
            Color.red,
            Color.blue
        )
    );

TO SAVE & LOAD

    data.Save("test.nbt");
    data = Nbt.Read("test.nbt");
    
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
    data.GetNbt("name");
    data.GetBoolArray("name");
    data.GetByteArray("name");
    data.GetIntArray("name");
    data.GetFloatArray("name");
    data.GetStringArray("name");
    data.GetVector2Array("name");
    data.GetVector3Array("name");
    data.GetQuaternionArray("name");
    data.GetColorArray("name");
    data.GetNbtArray("name");
    
    //EXAMPLE
    data.GetNbtArray("players")[0].GetString("name");


