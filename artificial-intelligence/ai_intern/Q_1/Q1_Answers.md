# Answers
## Q1

With no exact knowledge on the data or the details on the training or evaluation, pinpointing the problem exactly is a bit tricky.
- First though is we've got an OCR level problem since we've got letter confusion, it seems that we didn't feed it or train it on hard situations meaning our data is not properly augmented by blurring a little the letters or making harder to detect.
- The other thing that comes to mind looking at the problem is "another was fined for a vehicle of a similar make and color but with a slightly different registration number". Maybe the segmentation is leaving some color pixels that the OCR is considering, that is of course if the OCR is operation on colored crops rather than grayscale.

## Q2

- At first we need to train the OCR model on more complex data and hard situation, making the model robust and ready to tackle any kind of problem or letter recognition, the downside for this is training requires more data, even if augmented, just to avoid over-fitting and acquiring data needs time and resources.
- Second we need to look at our segmentation work, and make it grayscale, so it becomes resistant to colors, but this really depends on the contrast, black letters and white background? We're in good hands, white letters on red background? The contrast won't be that good. 
- Last thing, it may not be related to the exact model but to the whole pipeline itself, we really need focus on reducing the false positives, missing a faulty car is far permissible than fining an innocent one.

## Q3

That's quite obvious, the model will run, but not as accurately, we're talking about different dimensions, colors, letter fonts and sometimes even language! I'm thinking here of a base model that has variety, trained on big data from different countries and different situations, let that be our starting point then for each client we fine-tune or use feature extraction. It's illogical that the same model can perform with the same high accuracy in Japan and US at the same time!.
