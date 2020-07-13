<!-- 
# Gradient Utilities

## getLinearGradient

```ts
function getLinearGradient(
  minColor: string | number[],
  maxColor: string | number[],
  steps: number,
  inclusiveEnds: boolean = true,
  returnType: string = 'HEX',
)
```
### Parameters

#### minColor
- Type: `string | number[]`
- Default: `undefined`
- Description: `hex, rgb string, rgb array representation of the min color`

#### maxColor
- Type: `string | number[]`
- Default: `undefined`
- Description: `hex, rgb string, rgb array representation of max color`

#### steps
- Type: `number`
- Default: `undefined`
- Description: `The number of steps to be included in the gradient`

#### inclusiveEnds
- Type: `boolean`
- Default: `true`
- Description: `Flag to determine if the end steps in the gradient should represent minColor, maxColor`

#### returnType
- Type: `string`
- Default: `HEX`
- Description: `String representing returned color format - one of ['HEX', 'RGB_ARRAY', 'RGB_STRING']`

### Example Usage
```js{2,4}
 getLinearGradient('red', 'blue', 4, true, 'RGB_ARRAY')
 [ [255, 0, 0], [170, 0, 85], [85, 0, 170], [0, 0, 255] ]
 getLinearGradient('red', 'blue', 4, false, 'RGB_ARRAY')
 [ [204, 0, 51], [153, 0, 102], [102, 0, 153], [51, 0, 204] ]
```
function getLinearGradient(
  minColor: string | number[],
  maxColor: string | number[],
  steps: number,
  inclusiveEnds: boolean = true,
  returnType: string = 'HEX',




## getDataGradient

```ts 
function getDataGradient(
  minColor: string | number[],
  minVal: number,
  maxColor: string | number[],
  maxVal: number,
  steps: number,
  inclusiveEnds: boolean = true,
  returnType: string = 'HEX',
): DataGradientStep[]
```

### Parameters

#### minColor
- Type: `string | number[]`
- Default: `undefined`
- Description: `hex, rgb string, rgb array representation of the min color`

#### minVal
- Type: `number`
- Default: `undefined`
- Description: `Min value of the gradient`

#### maxColor
- Type: `string | number[]`
- Default: `undefined`
- Description: `hex, rgb string, rgb array representation of max color`

#### maxVal
- Type: `number`
- Default: `undefined`
- Description: `Max value of the gradient`

#### steps
- Type: `number`
- Default: `undefined`
- Description: `The number of steps to be included in the gradient`

#### inclusiveEnds
- Type: `boolean`
- Default: `true`
- Description: `Flag to determine if the end steps in the gradient should represent minColor, maxColor`

#### returnType
- Type: `string`
- Default: `HEX`
- Description: `String representing returned color format - one of ['HEX', 'RGB_ARRAY', 'RGB_STRING']`

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
``` -->
