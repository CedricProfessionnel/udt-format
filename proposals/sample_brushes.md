# Sample Brushes

> **_UNSTABLE_**

Sample brushes are a simple way to identify data by color. This can be helpful in collaborative sessions when people want to mark samples for review or indicate who completed the sample. It can also be used for reviewing the annotation of a machine learning algorithm by marking the annotation as one color, and the reviewed annotation as another.

## Usage

Place a `brush` attribute on some samples in `taskData` as shown below. The samples will be colored according to the specified brush.

```javascript
{
  "interface": {
    "type": "image_classification",
    "labels": [
      "valid",
      "invalid"
    ]
  },
  "samples": [
    {
      "brush": "review",
      "imageUrl": "https://s3.amazonaws.com/asset.workaround.online/example-jobs/sticky-notes/image1.jpg"
    },
    {
      "brush": "blue",
      "imageUrl": "https://s3.amazonaws.com/asset.workaround.online/example-jobs/sticky-notes/image2.jpg"
    }
  ]
}
```

If a sample does not have a brush, "complete" is used if it has corresponding `annotation` and "incomplete" is used if it does not have a corresponding `annotation`.

### Brush Colors

All colors are based on Material UI color names

- complete / blue
- review / deepOrange
- green
- purple
- pink
- cyan
- orange
- indigo
- incomplete / faded
- Any other string will have a color randomly assigned to it from the list above

## TODO

- Custom sample brushes should be automatically assigned a color
- Determine if other keys should imply brushes e.g. `inReview: true` could indicate `brush: "review"`

## Concerns

- Brush is not a name that makes it totally clear what this is used for
- It's not clear if the brush should be within `samples` or a new field
- The key on the sample should be `paint` or `brushColor`, not `brush`
