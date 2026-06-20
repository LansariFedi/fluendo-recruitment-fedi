# Answers
## Q1
With no exact knowledge on the data or the details on the training or evaluation, pinpointing the problem exactly is a bit tricky.
- First though is we've got an OCR level problem since we've got letter confusion, it seems that we didn't feed it or train it on hard situations meaning our data is not properly augmented by blurring a little the letters or making harder to detect.
- The other thing that comes to mind looking at the problem is "another was fined for a vehicle of a similar make and color but with a slightly different registration number". Maybe the segmentation is leaving some color pixels that the OCR is considering, that is of course if the OCR is operation on colored crops rather than grayscale.

## Q2