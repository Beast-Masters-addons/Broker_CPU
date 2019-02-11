## Description ##

A lightweight Data Broker plugin to visualize AddOn CPU/Memory usage, Framerate and Latency


- Automatic tooltip actualisation w/ configurable thresholds
- Can use a simple GameTooltip or advanced LibQTip
- No required librairies, they are just enhancements
- Can force to not use a library if it's detected but not needed
- Developed in order to use the bare minimum of cpu and memory
- Improved reading of data, you find a look addons assets and bad boys
- Garbage collection, detachable tooltip and more...

**Optionally you can:**

- Install LibQTip for cpudiff, memorydiff, icons columns & a cleaner tooltip
- Install LibDBIcon for a minimap icon
- The mod also supports AddonLoader
## Usages ##
Type /cpu, /brokercpu or /broker_cpu to show usage (or click the button with Broker bars)

## Helps/Tips ##
- **s/ms**
a value representing the access time to processor since you entered the world or a reloadui

- **KB/MB/Ko/Mo**
a value representing the current amount of memory used
But don't focalize on addons using a high number of memory, the screenshot of Carbonite vs QuestHelper shows you why, while Carbonite allocates more memory it has a tiny memory garbage creation and less cpu usage than QuestHelper that allocates less memory but has an horrible garbage creation, Carbonite shows a better control on performance than QuestHelper which increases the client's job to collect garbage memory and if you're experiencing freezing problems ingame you may look at an alternative to such bad boys, this is why it is useless to color gradient the amount of memory because you will just get an unreadable rainbow, the mod rather gradient the next % value explained below which is the most important)

- **%**
a value representing the difference between the old and current usage / 10
Like a speed meter you can use to compare X versus Y plugin, to check how performs your code, etc... if your mod goes red here, it most likely sucks hard!

BrokerCPU works with most LDB display, for a complete list see http://wiki.github.com/tekkub/libdatabroker-1-1/addons-using-ldb#ldbdisplay'>her
CPU profiling which is by default to OFF in the Blizzard client should remain OFF when you don't need it
Prefer the use of standalone libraries so BrokerCPU can report usage from addons and libraries separately, to do so follow these tips:

- You just install a standalone library like any other addon in the same Interface\AddOns\ folder
- The library must have a .toc file and the library folder must have the same name than the .toc file, example with DewdropLib the path should looks like Interface\AddOns\DewdropLib\DewdropLib.toc
- Then the longuest part is to remove the library you just installed in standalone from every addon you use that could embed it, then you are sure that only the standalone library is called and the consumed resources are correctly belonging to it.
- Some libraries are NOT to dis-embed, so if do you see the most popular embeds LibDataBroker, AceLibrary, LibStub, CallBackHandler, just leave them embedded, they are not designed to be standalone (If a library does not provide a .toc file it's not designed to be standalone)
