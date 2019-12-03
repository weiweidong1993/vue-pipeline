# vue-pipeline

One easy-to-use component to show beautiful responsive timeline like jenkins blue ocean plugin.

[中文](/docs/cn.md)

![sample](./resources/sample.png)

To get started, check out:

* [Demo](https://jinfang134.github.io/vue-pipeline/)


## LICENSE

**NOTE:** Vue Pipeline is licensed under [The MIT License](https://github.com/jinfang134/vue-pipeline/blob/master/LICENSE). Completely free, you can arbitrarily use and modify this plugin. If this plugin is useful to you, you can **Star** this repo, your support is my biggest motive force, thanks.


## Features

* Created Graph according your data dynamiclly
* Responsive web design
* svg component
* Fully configurable
* Via data attributes
* Show/Hide arrow
* 3 kinds of lines
* support graph and tree view
* Single node selection
* Different status for each node
* Different weight for each edge
* Different color for each node and edge


## Install

```
npm install vue-pipeline
```

```
import Vue from 'vue'
import VuePipeline from 'vue-pipeline'

Vue.use(VuePipeline)

```

## Props
### Props of Pipeline

| Name      | Type    | Default | Description                                          |
| --------- | ------- | ------- | ---------------------------------------------------- |
| width     | Number  | 1280    | The width of whole graph                             |
| height    | number  | 600     | Height                                               |
| x         | number  | 50      | The x coordinate of the starting point of the graph                         |
| y         | number  | 55      | The y coordinate of the starting point of the graph                        |
| xstep     | number  | 120     | The position horizontally from a previous node.  |
| ystep     | number  | 50      |  The position vertically from a previous node.    |
| data      | Array   | []      | data                                                 |
| lineStyle | string  | default | There are 3 types of line: ' default',' bessel','line' |
| showArrow | boolean | false   | whether show arrow for each line.                    |
|           |         |         |                                                      |

### Props for each node
| Name      | Type    | Default | Description                                          |
| --------- | ------- | ------- | ---------------------------------------------------- |
|name     | string | null | The title of each node  |
|hint     | string | null |  The hint of each node |
|status   | string | null |  Status of each node |
|next     | Array | [] |  The edge connected with this node |
| next: index    |    number   |    null     |   The index of another node of this edge |
| next: weight    |    number   |    null     |   The weight of this edge |

**Sample:**
```javascript
let data = [
    {
      name: "Start", hint: '1m23s', status: 'start', next: [
        { index: 1, weight: 2 }
      ]
    },
    {
      name: "Ammouncement Import", hint: '1m23s', status: 'success', next: [
        { index: 2, weight: 0 },
        { index: 4, weight: 2 }
      ]
    },
    {
      name: "Employee ID to Onboarding", hint: '2m23s', status: 'failure', next: [
        { index: 3, weight: 0 },

      ]
    },
    {
      name: "Personal Basic Info", hint: '2m23s', status: 'paused', next: [
        { index: 4, weight: 0 },
      ]
    },
    { name: "End ", hint: '2m23s', status: 'end', next: [] },
  ]
```

## Events

| Name   | Params | Description                 |
| ------ | ------ | --------------------------- |
| @click | node   | Occurs when node is clicked |

## Function

| Name   | params | Description                  |
| ------ | ------ | ---------------------------- |
| render | Node   | render the whole graph again |


## Contributing

If you find any bugs and/or want to contribute, feel free to create issues or submit pull requests.

Thanks!

## Local Development
```
cd demo
yarn install

// Compiles and hot-reloads for development
yarn run serve
```


### Lints and fixes files
```
yarn run lint
```
