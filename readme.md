## react-native-picker-scrollview
[![All Contributors](https://img.shields.io/badge/all_contributors-4-orange.svg?style=flat-square)](#contributors-)

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

## Contributors ✨

Thanks goes to these wonderful people :shipit:

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<table>
  <tr>
    <td align="center"><a href="https://github.com/kasinskas"><img src="https://avatars1.githubusercontent.com/u/22332217?v=4" width="64px;" alt="Rokas Kašinskas"/><br /><sub><b>Rokas Kašinskas</b></sub></a><br /><a href="https://github.com/lukebars/rn-scrollable-picker/commits?author=kasinskas" title="Code">💻</a></td>
    <td align="center"><a href="https://github.com/lukebars"><img src="https://avatars0.githubusercontent.com/u/46403446?v=4" width="64px;" alt="Lukas Baranauskas"/><br /><sub><b>Lukas Baranauskas</b></sub></a><br /><a href="https://github.com/lukebars/rn-scrollable-picker/commits?author=lukebars" title="Code">💻</a></td>
    <td align="center"><a href="https://github.com/veizz"><img src="https://avatars3.githubusercontent.com/u/1176926?v=4" width="64px;" alt="veizz"/><br /><sub><b>veizz</b></sub></a><br /><a href="https://github.com/lukebars/rn-scrollable-picker/commits?author=veizz" title="Code">💻</a></td>
    <td align="center"><a href="https://www.linkedin.com/in/rafanascmag/"><img src="https://avatars1.githubusercontent.com/u/10750521?v=4" width="64px;" alt="Rafael Magalhães"/><br /><sub><b>Rafael Magalhães</b></sub></a><br /><a href="https://github.com/lukebars/rn-scrollable-picker/commits?author=RafaelMagalhaesN" title="Tests">⚠️</a></td>
  </tr>
</table>

<!-- markdownlint-enable -->
<!-- prettier-ignore-end -->
<!-- ALL-CONTRIBUTORS-LIST:END -->

This project follows the [all-contributors](https://github.com/all-contributors/all-contributors) specification. Contributions of any kind welcome!