namesex_light
-------------

namesex_light is a lighweight package that predicts the gender tendency of a Chinese given name. The package adopted a L2 regularized logistic regression to predict gender tendency. The model was trained on 10,730 Chinese given names (in traditional Chinese) with reliable gender lables collected from public data. This package contains a trained model and a predict() function that takes a list of names and output predicted labels (1 for male and 0 for female) or probability of being a male name.

Use pip/pip3 to install namesex_light.::

    pip install namesex_light

To use namesex_light, pass in a array or list of given names to the predict() method. For each element in the input list, this method returns 1 or 0 for male or female prediction. Set "predprob = True" to return probability of being a male name. The followin is a simple sample code.::


    >>> import namesex_light
    >>> nsl = namesex_light.namesex_light()
    >>> nsl.predict(['民豪', '愛麗', '志明'])
    array([1, 0, 1])
    >>> nsl.predict(['民豪', '愛麗', '志明'], predprob=True)
    array([0.99968932, 0.00530066, 0.9938986 ])

Note that namesex_light was trained using Chinese given names only. However, it may be used to classifier translated names as well::

    >>> nsl.predict(['阿波羅', '阿波羅', '雷', '艾美', '布蘭妮', '阿曼達'])
    array([1, 1, 1, 0, 0, 1])

This module is intended for a quick plug-and-play. The original training dataset is not included.
