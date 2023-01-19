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
 
 
 
 doggy-dentures made the code
