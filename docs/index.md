# findNeedles Method
A reference document for a method that finds a set of words inside a text, and displays how many times it finds a match for each word.

## Syntax

The following code sample represents a *find needles in haystack method* written in **Java**:

```java
public static void findNeedles(String haystack, String[] needles) {
	if (needles.length > 5) {
		System.err.println("Too many words!");
	} else {
		int[] countArray = new int[needles.length];
		for (int i = 0; i<needles.length; i++) {
			String[] words = haystack.split("[ \"\'\t\n\b\f\r]", 0);
			for (int j = 0; j<words.length; j++) {
				if (words[j].compareTo(needles[i]) == 0) {
					countArray[i]++;
				}
			}
		}
		for (int j = 0; j<needles.length; j++) {
			System.out.println(needles[j] + ": " + countArray[j]);
		}
	}
}
```
### Parameters

The method receives two parameters:
```java
public static void findNeedles(String haystack, String[] needles)
```
* ``haystack``: the string containing the available words 
* ``needles``: the words to find in the haystack 

### Execution Condition

This method only works for a set of a ***maximum*** of *five words*. If the ``needles`` array contains more than five elements, an error message is displayed.

```java
if (needles.length > 5) {
		System.err.println("Too many words!");
```

### Haystack Split and Word Comparison

If the condition allows, the method creates an array to store the count of each of the words in ``needles``.
```java
else {
		int[] countArray = new int[needles.length];
```

The following for loop separates the ``haystack`` string into single words using the ``split`` Java method and stores them in a new array of strings called ``words``. 
```Java
for (int i = 0; i<needles.length; i++) {
	String[] words = haystack.split("[ \"\'\t\n\b\f\r]", 0);
	for (int j = 0; j<words.length; j++) {
		if (words[j].compareTo(needles[i]) == 0) {
			countArray[i]++;
		}
	}
}
```
The ``split`` method takes two arguments: a *regular expression* and a *limit*. In this case:

* ``"[\"\'\t\n\b\f\r]"`` : This regular expression separates words from the text when it finds **double quotes**, **single quotes**, **tabs**, **blank spaces**, and **line breaks**.
* ``0``: The ``0`` limit means that splitting will happen as many times as needed.

**Note:** To know more about the ``split`` method, visit the [String Class documentation](https://docs.oracle.com/javase/7/docs/api/java/lang/String.html#split) and navigate to the **split** section.

The inner **for** loop compares, using the ``compareTo`` Java method, each string of the ``words`` array with the word in the current position of the ``needles`` array. 
```Java
for (int j = 0; j<words.length; j++) {
		if (words[j].compareTo(needles[i]) == 0) {
			countArray[i]++;
		}
	}
}
```
For each comparison, the code checks if the ``compareTo`` method returned a ``0``, indicating a match between both words. If there is a match, it increases the counter for that word.

**Note:** To know more about the ``compareTo`` method, visit the [Comparable documentation](https://docs.oracle.com/javase/7/docs/api/java/lang/Comparable.html).

### Calling the Method and Displaying the Output 

Calling the method returns each word in ``needles`` and the number of times that it was found inside the ``haystack`` string.

Here is an example of calling the method:
```Java
String[] needles = new String[]{"hello","hollo","hullo", "hillo", "hallo"};
    
findNeedles("hello\'hello\thello\bwhole'\nhullo'hullo hillo", needles);
```
Which returns the following:
```Bash
hello: 3
hollo: 0
hullo: 2
hillo: 1
hallo: 0
```

# Questions and Feedback

If I were to ask the developer about the code, these are the questions I would ask:

* Why is it limited to only five words?
* Can it be implemented more generally, for example, use it also for numbers?
* Is there an easier regular expression to split the text?

If I were to make suggestions, I would start with something positive and then move to the feedback. Something like this:

Hi, "Developer"

I reviewed the code and documented its reference material. Although I find it easy to understand and well structured, I noticed a couple of ways to improve it.
Here are my thoughts:

*  Take the ``words`` array declaration outside of the loop. In this way, the array will only be created once instead of in every iteration, saving memory.
* Declare only one counter instead of an array of counters. You can do it before looping and set it back to ``0`` after each *needle* comparison.

Here is how the code would look like with the suggestions:

```Java
public static void findNeedles(String haystack, String[] needles) {
    if (needles.length > 5) {
        System.err.println("Too many words!");
    } else {
        int count = 0;
        String[] words = haystack.split("[\"\'\t\n\b\f\r]", 0);
        for (int i = 0; i < needles.length; i++) {
            for (int j = 0; j < words.length; j++) {
                if (words[j].compareTo(needles[i]) == 0) {
                        count++;
                }
            }
            System.out.println(needles[i] + ": " + count);
            count = 0;
        }
    }
}
```
