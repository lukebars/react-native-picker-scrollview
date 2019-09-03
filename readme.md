## react-native-picker-scrollview

a pure and smart js picker, highly customizable.

auto height detection

![example](./res/demo.gif)


### usage

```shell
npm install react-native-picker-scrollview --save
```

props:

`fixedHeight` - locks scrollable picker wrapper height to given wrapperHeight

```jsx
import React, {Component} from 'react';
import ScrollPicker from 'rn-scrollable-picker';

export default class SimpleExample extends Component {


    handleClick = (index, options, onValueChange) => {
        this.sp.scrollToIndex(index);   // select 'c'
        onValueChange(options[index]);
    }

    render() {
        return(
            <ScrollPicker
                ref={(sp) => {this.sp = sp}}
                dataSource={options}
                selectedIndex={0}
                itemHeight={ITEM_HEIGHT}
                highlightColor={'#fff'}
                wrapperHeight={500}
                wrapperStyle={{
                    backgroundColor: 'transparent'
                }}
                renderItem={(data, index, isSelected) => {
                    return(
                        <TouchableOpacity 
                        onPress={() => this.handleClick(index, options, onValueChange)} 
                        style={{height: ITEM_HEIGHT}}>
                            <Text style={isSelected ? {
                                    color: '#fff',
                                    textAlign: 'center',
                                    fontSize: 34,
                                    fontFamily: 'HK Grotesk',
                                    lineHeight: 50,
                                    height: 50,
                                    fontWeight: 'bold'
                                } : {
                                    color: '#fff',
                                    textAlign: 'center',
                                    fontSize: 20,
                                    fontFamily: 'HK Grotesk',
                                    lineHeight: 50,
                                    height: 50,
                                    fontWeight: '300'
                                }}
                            >
                                {data}
                            </Text>
                        </TouchableOpacity>
                    )
                }}
                onValueChange={(data, selectedIndex) => {
                    onValueChange(options[selectedIndex]);
                }}
            />
    );
    }
}

```
