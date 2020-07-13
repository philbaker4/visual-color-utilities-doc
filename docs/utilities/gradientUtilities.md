# Gradient Utilities

## getLinearGradient

```ts
function getLinearGradient(
  minColor: string | number[],
  maxColor: string | number[],
  steps: number,
  inclusiveEnds: boolean = true,
  returnType: string = 'HEX',
): string[] | number[][]
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

interface DataGradientStep {
  minVal: number;
  maxVal: number;
  color: string | number[];
}
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

### Example Usage

```js{2-23,26-47}
getDataGradient('red', 0, 'blue', 1, 4, true, 'RGB_ARRAY')
[
    {
      minVal: 0,
      maxVal: 0.25,
      color: [255, 0, 0],
    },
    {
      minVal: 0.25,
      maxVal: 0.5,
      color: [170, 0, 85],
    },
    {
      minVal: 0.5,
      maxVal: 0.75,
      color: [85, 0, 170],
    },
    {
      minVal: 0.75,
      maxVal: 1,
      color: [0, 0, 255],
    },
]

getDataGradient('red', 0, 'blue', 1, 4, false, 'RGB_ARRAY')
[
    {
      minVal: 0,
      maxVal: 0.25,
      color: [204, 0, 51],
    },
    {
      minVal: 0.25,
      maxVal: 0.5,
      color: [153, 0, 102],
    },
    {
      minVal: 0.5,
      maxVal: 0.75,
      color: [102, 0, 153],
    },
    {
      minVal: 0.75,
      maxVal: 1,
      color: [51, 0, 204],
    },
]
```

## getMultiColorDataGradient

```ts 
function getMultiColorDataGradient(
  multiColorGradientDefinition: GradientDefinition[],
  steps: number = 100,
  returnType: string = 'HEX',
): DataGradientStep[]

interface GradientDefinition {
  minVal: number;
  minColor: string | number[];
  maxVal: number;
  maxColor: string | number[];
}

interface DataGradientStep {
  minVal: number;
  maxVal: number;
  color: string | number[];
}
```

### Parameters

#### steps
- Type: `GradientDefinition[]`
- Default: `undefined`
- Description: `Array of GradientDefinition objects`

#### steps
- Type: `number`
- Default: `undefined`
- Description: `The number of steps to be included in the gradient`

#### returnType
- Type: `string`
- Default: `HEX`
- Description: `String representing returned color format - one of ['HEX', 'RGB_ARRAY', 'RGB_STRING']`


### Example Usage
```js{16-29}
const multiColorGradientDefinition = [
  {
    minVal: 0,
    minColor: 'red',
    maxVal: 1,
    maxColor: 'blue',
  },
  {
    minVal: 1,
    minColor: 'blue',
    maxVal: 3,
    maxColor: 'yellow',
  },
];
getMultiColorDataGradient(multiColorGradientDefinition, 12, 'RGB_ARRAY')
[
    { color: [204, 0, 51], minVal: 0, maxVal: 0.25 },
    { color: [153, 0, 102], minVal: 0.25, maxVal: 0.5 },
    { color: [102, 0, 153], minVal: 0.5, maxVal: 0.75 },
    { color: [51, 0, 204], minVal: 0.75, maxVal: 1 },
    { color: [28, 28, 227], minVal: 1, maxVal: 1.25 },
    { color: [57, 57, 198], minVal: 1.25, maxVal: 1.5 },
    { color: [85, 85, 170], minVal: 1.5, maxVal: 1.75 },
    { color: [113, 113, 142], minVal: 1.75, maxVal: 2 },
    { color: [142, 142, 113], minVal: 2, maxVal: 2.25 },
    { color: [170, 170, 85], minVal: 2.25, maxVal: 2.5 },
    { color: [198, 198, 57], minVal: 2.5, maxVal: 2.75 },
    { color: [227, 227, 28], minVal: 2.75, maxVal: 3 },
]
```



## getColorFromDataGradient 

```ts
function getColorFromDataGradient(
  minColor: string | number[],
  minVal: number,
  maxColor: string | number[],
  maxVal: number,
  steps: number,
  value: number,
  inclusiveEnds: boolean = true,
  returnType: string = 'HEX',
  byStep: boolean = true,
): string | number[]
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

#### value
- Type: `number`
- Default: `undefined`
- Description: `The value for which you are trying to find a color`

#### inclusiveEnds
- Type: `boolean`
- Default: `true`
- Description: `Flag to determine if the end steps in the gradient should represent minColor, maxColor`

#### returnType
- Type: `string`
- Default: `HEX`
- Description: `String representing returned color format - one of ['HEX', 'RGB_ARRAY', 'RGB_STRING']`

#### byStep
- Type: `boolean`
- Default: `true`
- Description: `Flag to determine if the color should represent the step that the value falls in or a direct linear interpolation between the two ends of the gradient`


### Example Usage
```js{3,6,9,12}
// exclusiveEnds - by step
  getColorFromDataGradient('red', 0, 'blue', 1, 4, 0.1, false, 'RGB_ARRAY', true)
  [204, 0, 51]
// exclusiveEnds - direct interpolation
  getColorFromDataGradient('red', 0, 'blue', 1, 4, 0.1, false, 'RGB_ARRAY', false)
  [230, 0, 26]
// inclusiveEnds - by step
  getColorFromDataGradient('red', 0, 'blue', 1, 4, 0.1, true, 'RGB_ARRAY', true)
  [255, 0, 0]
// inclusiveEnds - direct interpolation
  getColorFromDataGradient('red', 0, 'blue', 1, 4, 0.1, true, 'RGB_ARRAY', false)
  [230, 0, 26]
```


## getColorFromMultiColorDataGradient

```ts
function getColorFromMultiColorDataGradient(
  multiColorGradientDefinition: GradientDefinition[],
  steps: number,
  value: number,
  returnType?: string,
  byStep: boolean = true,
) string | number[]


interface GradientDefinition {
  minVal: number;
  minColor: string | number[];
  maxVal: number;
  maxColor: string | number[];
}
```

### Parameters

#### steps
- Type: `GradientDefinition[]`
- Default: `undefined`
- Description: `Array of GradientDefinition objects`

#### steps
- Type: `number`
- Default: `undefined`
- Description: `The number of steps to be included in the gradient`

#### value
- Type: `number`
- Default: `undefined`
- Description: `The value for which you are trying to find a color`

#### returnType
- Type: `string`
- Default: `HEX`
- Description: `String representing returned color format - one of ['HEX', 'RGB_ARRAY', 'RGB_STRING']`

#### byStep
- Type: `boolean`
- Default: `true`
- Description: `Flag to determine if the color should represent the step that the value falls in or a direct linear interpolation between the two ends of the gradient`


### Example Usage
```js{18,21}
const multiColorGradientDefinition = [
  {
    minVal: 0,
    minColor: 'red',
    maxVal: 1,
    maxColor: 'blue',
  },
  {
    minVal: 1,
    minColor: 'blue',
    maxVal: 3,
    maxColor: 'yellow',
  },
];

// byStep
getColorFromMultiColorDataGradient(multiColorGradientDefinition, 12, 0.5, 'RGB_ARRAY', true)
[102, 0, 153]
// not byStep
getColorFromMultiColorDataGradient(multiColorGradientDefinition, 12, 0.5, 'RGB_ARRAY', false)
[128, 0, 128]

```