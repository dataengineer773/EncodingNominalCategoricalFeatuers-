We have a feature with nominal classes that has no intrinsic ordering (e.g., apple, pear, banana) and you
want to encode the feature into numerical values, One-hot encode the feature using scikit-learn’s LabelBinarizer We can use the classes_ attribute to output the classes
If we want to reverse the one-hot encoding, we can use inverse_transform, We can even use pandas to one-hot encode the feature, One helpful ability of scikit-learn is to handle a situation where each observation lists multiple classes
Once again, we can see the classes with the classes_ method, We might think the proper strategy is to assign each class a numerical value (e.g., Texas = 1, California
= 2). However, when our classes have no intrinsic ordering (e.g., Texas isn’t “less” than California), our
numerical values erroneously create an ordering that is not present.
The proper strategy is to create a binary feature for each class in the original feature. This is often called
one-hot encoding (in machine learning literature) or dummying (in statistical and research literature).
Our solution’s feature was a vector containing three classes (i.e., Texas, California, and Delaware). In
one-hot encoding, each class becomes its own feature with 1s when the class appears and 0s otherwise.
Because our feature had three classes, one-hot encoding returned three binary features (one for each
class). By using one-hot encoding we can capture the membership of an observation in a class while
preserving the notion that the class lacks any sort of hierarchy.
Finally, it is often recommended that after one-hot encoding a feature, we drop one of the one-hot
encoded features in the resulting matrix to avoid linear dependence.
