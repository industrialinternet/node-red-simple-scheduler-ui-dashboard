# node-red-simple-scheduler-ui-dashboard

A very very simple scheduler with 12 schedule items.
The scheduler will run on the hour and within the minuet sepecifed.
So if if an item start was 11.21 and depending when the NR started the item would run at 11.21: from 0 - 59 sec.
So don't expect it to run bang on 11.21.  

![UI](https://github.com/industrialinternet/node-red-simple-scheduler-ui-dashboard/blob/master/shed-ui.png?raw=true)

**install** 
1. Import flow
2. 
Context is at flow level and requires persistant storage to be enabled.
Edit settings.js under contextStorage add file key as below

```javascript
contextStorage: {
	default: { module: "memory"},
	file: { module: 'localfilesystem', 
		config: {
			cache: true,
			flushInterval:	30
		}
	}
},
```
3. Restart node-red
4. click create inject node to create JSON needed for the **scheduler** you can edit this manualy if you like.
5. you can change the run freqency of the scheduler which is defaulted to 30 sec. By editing the un@ inject node. 
![flow](https://raw.githubusercontent.com/industrialinternet/node-red-simple-scheduler-ui-dashboard/master/simple-shed-flow.png)
