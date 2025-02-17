# react-native-nested-listview

UI component for React Native that allows to create a listview with N levels of nesting

![platforms](https://img.shields.io/badge/platforms-Android%20%7C%20iOS-brightgreen.svg?style=flat-square)
[![CircleCI](https://circleci.com/gh/fjmorant/react-native-nested-listview.svg?style=shield)](https://circleci.com/gh/fjmorant/react-native-nested-listview)
[![codecov](https://codecov.io/gh/fjmorant/react-native-nested-listview/branch/master/graph/badge.svg)](https://codecov.io/gh/fjmorant/react-native-nested-listview)
[![npm](https://img.shields.io/npm/v/react-native-nested-listview.svg?style=flat-square)](https://www.npmjs.com/package/react-native-nested-listview)
[![github release](https://img.shields.io/github/release/fjmorant/react-native-nested-listview.svg?style=flat-square)](https://github.com/fjmorant/react-native-nested-listview/releases)
[![CodeFactor](https://www.codefactor.io/repository/github/fjmorant/react-native-nested-listview/badge)](https://www.codefactor.io/repository/github/fjmorant/react-native-nested-listview)

## Table of contents

1. [Show](#show)
1. [Usage](#usage)
1. [Props](#props)
1. [Examples](#examples)
1. [Roadmap](#roadmap)

## Show

![react-native-nested-listview](https://i.imgur.com/Y3VFTry.gif)
![react-native-nested-listview](https://i.imgur.com/nJvl0ZT.gif)

## Usage

```
yarn add react-native-nested-listview
```

```javascript
import NestedListView, {NestedRow} from 'react-native-nested-listview'

const data = [{title: 'Node 1', items: [{title: 'Node 1.1'}, {title: 'Node 1.2'}]}]

<NestedListView
  data={data}
  getChildrenName={(node) => 'items'}
  onNodePressed={(node) => alert('Selected node')}
  renderNode={(node, level, isLastLevel) => (
    <NestedRow
      level={level}
      style={styles.row}
    >
      <Text>{node.title}</Text>
    </NestedRow>
  )}
/>
```

## Props

### NestedListView

| Prop                     | Description                                                                                                                                                              | Type     | Default      |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------- | ------------ |
| **`data`**               | Array of nested items                                                                                                                                                    | Array    | **Required** |
| **`renderNode`**         | Takes a node from data and renders it into the NestedlistView. The function receives `{node, level, isLastLevel}` (see [Usage](#usage)) and must return a React element. | Function | **Required** |
| **`getChildrenName`**    | Function to determine in a node where are the children, by default NestedListView will try to find them in **items**                                                     | Function | **items**    |
| **`onNodePressed`**      | Function called when a node is pressed by a user                                                                                                                         | Function | Not required |
| **`extraData`**          | A marker property for telling the list to re-render                                                                                                                      | Boolean  | Not required |
| **`keepOpenedState`**    | Prop for keeping the opened state of each node when data passed to the list changes                                                                                      | Boolean  | Not required |
| **`initialNumToRender`** | Prop for setting the initial amount of items to render.                                                                                                                  | number   | Not required |

### NestedRow

| Prop           | Description                 | Type      | Default      |
| -------------- | --------------------------- | --------- | ------------ |
| **`height`**   | Height of the row           | number    | 50           |
| **`children`** | Content of the NestedRow    | Component | **Required** |
| **`level`**    | Level where a given node is | number    | **Required** |
| **`style`**    | NestedRow container style   | Style     | Not required |

## Examples

You can find examples [here](https://github.com/fjmorant/react-native-nested-listview-examples).

| Version App | React Native | Library |
| ----------- | ------------ | ------- |
| 1.0.0       | 0.67.1       | 0.11.1  |

## Roadmap

I have moved the roadmap of this library to this trello board so that it can be easier to add more things and like that it doesn't create issues in GitHub if I need to create a ticket

[Roadmap Trello Board](https://trello.com/b/IOMR8gFw)

## Development

In other to start watch mode and develop the library with the examples project (described above), you need to have installed the following npm packages:

- `npm -g json`
- `npm -g wml`

And have the library and examples project in the same root folder, example:

- root
  - react-native-nested-listview
  - react-native-nested-listview-examples

After the previous steps you can then run the following command:

`yarn start-watch`

and then you can start the examples app as usual:

`yarn ios` or `yarn android`

When you finish with watch mode remember to stop it to get back to normal like this:

`yarn stop-watch`

## Invite me a coffee

If you want to invite me for a coffee after enjoying this library or just for fun.

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/D1D16TF2V)

Thanks
