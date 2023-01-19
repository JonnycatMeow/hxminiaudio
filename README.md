# hxminiaudio
not my code 
 
# How to setup it up 
 1. add the files into the source code. 
 2. paste this code on Paths.hx  
   ``` 
   //opus audio file feature
	static public function opus(key:String)
	{
		if (FileSystem.exists(file(key, "music", "opus")))
			return file(key, "music", "opus");
		return music(key);
	}  
 ``` 
 2. go in playstate and pate this variables 
 ``` 
 var music:AudioStreamThing;
 var vocals:AudioStreamThing;  
 ``` 
 3. go into playstate where the override public function create paste this there 
 ```
music = new AudioStreamThing(Paths.opus(SONG.song + "_Inst"), true); 
```
 
 doggy-dentures made the code
