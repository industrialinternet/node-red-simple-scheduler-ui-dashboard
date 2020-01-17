# node-red-simple-scheduler-ui-dashboard

A very very simple scheduler with 12 schedule items.

![UI](https://github.com/industrialinternet/node-red-simple-scheduler-ui-dashboard/blob/master/shed-ui.png?raw=true)


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

![flow](https://raw.githubusercontent.com/industrialinternet/node-red-simple-scheduler-ui-dashboard/master/simple-shed-flow.png)
