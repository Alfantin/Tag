This framework is simple and flexible binary data format inspired from Minecraft Named Binary Tag format.

I created it for my personal unity projects to save game, level, settings etc and network communication.

I did't test yet. I still developing it.

    //CREATE
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

	//SAVE
    data.Save("test.nbt");
    
	//LOAD
    data = Nbt.Read("test.nbt");
    
	//READ SAMPLE
    data.GetNbtArray("players")[0].GetString("name");
