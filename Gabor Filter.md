Word for [[Kernel Methods]]
Uses Gaussian surface

#### How the human eyeball works (image classification)

Have an image - deide how big your gabor filter is (in pixels)
- If gabor filter is 9x9, result image loses 9 pixels on all sides

1. Apply simple gabor filters to image to extract simple features - max pool the results into one result
2. Apply more complex gabor filters (combinations of prev filters) to the result map
3. Repeat step 2, gabor filters combination of images in part 2
4. Serialize, throw into a classifier (perceptron, SVM, naive bayesian, etc)
5. If inaccurate, back propogate - basically you're fine tuning the feature extraction by changing the prototypes
	1. First make adjustment to classification tool
	2. Can treat all results as kernel
	3. Kernel is adjusted to high response on the result map
	4. Break down kernel into prototypes
	5. Make adjustments to first layer
	6. repeat


