Nuclex.Cloning
==============

This is a C# based .NET 4 library that is used to deep clone objects, whether they are serializable or not. 
It intends to be much faster than the normal binary serialization method of deep cloning objects.

This is basically just slightly tidied up code from http://blog.nuclex-games.com/mono-dotnet/fast-deep-cloning/, and 
if it works well I intend to publish it to NuGet as well, as currently at 03/Dec/2013 there are only 2 other deep cloning libraries (none of which is as flexible as this, I believe).

This library can be used staticly or injected using the ICloneFactory interface.

Usage
--------------

	var original = new ComplicatedStuff(42);

	ComplicatedStuff clone1 = ReflectionCloner.DeepFieldClone(original);

or
	// you need to make sure you are invoking via ICloneFactory, the var keyword will not work since the implemented methods are static
	 ICloneFactory cloner = new ReflectionCloner(); 
	 var clone = cloner.DeepFieldClone(original);