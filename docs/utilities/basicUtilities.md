# Basic Utilities

## getHex
```ts
function getRGBString(color: string | number[])
```
### Parameters

#### color
- Type: `string | number[]`
- Default: `undefined`
- Description: `HEX, RGB_STRING, or RGB_ARRAY representation of a color`


### Example Usage
```js{2}
getHex('rgb(255, 255, 0)')
'#ffff00'
```

## getRGBString
```ts
function getRGBArray(color: string | number[])
```
### Parameters

#### color
- Type: `string | number[]`
- Default: `undefined`
- Description: `HEX, RGB_STRING, or RGB_ARRAY representation of a color`

### Example Usage
```js{2}
getRGBString([255, 255, 0])
'rgb(255, 255, 0)'
```

## getRGBArray
```ts
function getHex(color: string | number[])
```
### Parameters

#### color
- Type: `string | number[]`
- Default: `undefined`
- Description: `HEX, RGB_STRING, or RGB_ARRAY representation of a color`

### Example Usage
```js{2}
getRGBArray('#ffff00')
[255, 255, 0]
```


## changeSaturation

### Parameters

#### color
- Type: `string | number[]`
- Default: `undefined`
- Description: `HEX, RGB_STRING, or RGB_ARRAY representation of a color`

#### percent
- Type: `number`
- Default: `undefined`
- Description: `Decimal representation of percent change`

#### returnType
- Type: `string`
- Default: `HEX`
- Description: `String representing returned color format - one of ['HEX', 'RGB_ARRAY', 'RGB_STRING']`

### Example Usage
```js{2,4}
const lighter = changeSaturation('rgb(255, 0, 0)', .25, 'RGB_STRING')
'rgb(255, 64, 64)'
const darker = changeSaturation('rgb(255, 0, 0)', -.25, 'RGB_STRING')
'rgb(191, 0, 0)'
```
