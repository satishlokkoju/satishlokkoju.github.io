---
title: "TensorFlow JS"
description: "Neural network implementation on a web browser"
publishDate: 2018-09-05
image: /assets/images/posts/tensorflowjs.webp
tags:
  - tensorflow
  - javascript
draft: false
---

As a Javascript lover, and doing data science as my full time job, TensorFlow JS is like a dream come through, now you can run lightweight ML models directly in the web browser and share them!

## Why TensorFlow JS
- There is no installation, users can access your model via web browser, you can share your machine learning capability by hosting it on the web
- Allowing users to train a model with their data without first handling to you

## Let's begin
Open your favourite editor, create a new .html file (for example *tfjs.html*), and add the following code to your HTML file:

```html
<html>
  <head>
    <!-- Load TensorFlow.js -->
    <script src="https://cdn.jsdelivr.net/npm/@tensorflow/tfjs@0.13.0"> </script>

    <!-- Place your code in the script tag below. You can also use an external .js file -->
    <script>
      console.log('hi, this works');
    </script>
  </head>

  <body>
    <h4>Check your browser's console</h4>
  </body>
</html>
```

## Train your first model

Let's train our first model and store it to a variable called `model`. This model has 3 layers each with a specific shape.

```javascript
// Define a model
const model = tf.sequential();

// First layer must specify the input shape
model.add(tf.layers.dense({
  units: 256, 
  inputShape: [784], 
  activation: 'relu'
}));

// Add another layer
model.add(tf.layers.dense({
  units: 128, 
  activation: 'relu'
}));

// Output layer
model.add(tf.layers.dense({
  units: 10, 
  activation: 'softmax'
}));
```

Next, we need to compile our model. We need to specify the optimizer, loss function and metrics we would like to track while training.

```javascript
// Compile the model
model.compile({
  optimizer: 'sgd',
  loss: 'categoricalCrossentropy',
  metrics: ['accuracy']
});
```

In order to train a model, we need data. Let's create a dummy dataset - random input and random output.

```javascript
// Generate dummy data for training
const data = tf.randomNormal([100, 784]);
const labels = tf.randomUniform([100, 10]);

function onEpochEnd(epoch, logs) {
  console.log(`Epoch: ${epoch} Loss: ${logs.loss} Accuracy: ${logs.acc}`);
}
```

Now let's train our model with the following configuration:

```javascript
// Train the model with 5 epochs and batch size of 32
// We also monitor the training process with our callback function
model.fit(data, labels, {
  epochs: 5,
  batchSize: 32,
  callbacks: { onEpochEnd }
}).then(info => {
  console.log('Final accuracy', info.history.acc);
});
```

That's it! You've trained your first neural network in a web browser using TensorFlow.js. You can expand on this by loading real-world data, or importing pre-trained models.

## Resources

For more information, check out these resources:
- [TensorFlow.js Official Website](https://www.tensorflow.org/js)
- [TensorFlow.js Examples](https://github.com/tensorflow/tfjs-examples)
- [TensorFlow.js API Reference](https://js.tensorflow.org/api/latest/)
