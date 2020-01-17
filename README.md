# node-red-simple-scheduler-ui-dashboard

A very very simple scheduler with 12 schedule items.
The scheduler will run on the hour and within the minuet sepecifed.
So if an item start was 11.21 and depending when the NR started the item would run somewhere between 11.21:**00** to 11.21:**59**
So don't expect it to run bang on 11.21:**00**  

**install** 
1. Import flow
2. Context is at flow level and requires persistant storage to be enabled.
Edit **settings.js** under contextStorage add file key as below

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

**scheduler output**
```javascript
msg.payload:  200;      // value set 
msg.item:     'shd-1';  // schedule item 1
msg.msgType:  'shdEvent';
```

**Testing & Reset**
An item can only be scheduled once a day.
And end time event can only run if an start event has run.
If you testing use the rest inject to clear all run events.
The last run event will displayed on UI, note this is cleared on Deploy.

**Gotchas**
On NR restart/deploys sometimes schedule item 1 is selected and item details are Not displayed.
Just click 1 in the select grid and details will appear. 


**To do's**
Impliment start and end date settings.

![UI](https://github.com/industrialinternet/node-red-simple-scheduler-ui-dashboard/blob/master/shed-ui.png?raw=true)
