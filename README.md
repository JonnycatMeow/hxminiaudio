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
4. go into playstate where the function startSong paste this there
 ``` 
 AudioStreamThing.playGroup(); 
 ```
 5. go into playstate where you will find a function called generateSong 
    ```  
    if (SONG.needsVoices)
		{
			// vocals = new FlxSound().loadEmbedded(Paths.music(curSong + "_Voices"));
			vocals = new AudioStreamThing(Paths.opus(curSong + "_Voices"), true);
		}
		else
			vocals = new AudioStreamThing(''); 
    ```
     
     6. go into playstate where you will find a function called openSubState and paste it there  
      ``` 
      if (music != null)
			{
				// music.pause();
				// vocals.pause();
				AudioStreamThing.pauseGroup();
			}
	``` 
	
	7. go into playstate where you will find a function called  closeSubState and paste it there  where it says if paused  
	``` 
	if (music != null && !startingSong)
			{
				AudioStreamThing.playGroup();
				resyncVocals();
			} 
            ```  
      
        
	
	
      8. and finally paste this into the override public function destroy 
       ``` 
       AudioStreamThing.destroyGroup(); 
       ```
       
 doggy-dentures made the code
