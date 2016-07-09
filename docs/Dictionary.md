# AutoCorrect.Dictionary
The Dictionary class is the main class you'll be interacting with when using this Python module. A Dictionary instance
is a special dictionary that is able to learn words and autocorrect texts using a simple learning-algorithm.

### `.find_longer_words`
Find all words in the AutoCorrect dictionary that start with a given prefix. If no prefix is given, all words in the
dictionary are returned. If there are no words with a given prefix, an empty list is returned.

##### Parameters
| Name   | Description                       | Required |
|--------|-----------------------------------|----------|
| prefix | The prefix words should have.     | No       |

### `.find_similar_words`
Find all words in the AutoCorrect dictionary that are similar to a given word using several different algorithms.

This method will return an descending (ordered on rating) list of tuples formatted as `('word', rating)`, where the
rating is a number that indicates how likely it is that that word is the intended word.

##### Parameters
| Name    | Description                               | Required |
|---------|-------------------------------------------|----------|
| word    | The word for which to find similar words. | Yes      |
| follows | The word the given word follows.          | No       |
| leads   | The word the given word leads.            | No       |

### `.find_word`
Find a word in the AutoCorrect dictionary. A tuple containing information about that word is
returned if the word is found. Otherwise, if the word wasn't found, a `LookupError` will be thrown.

##### Parameters
| Name | Description                       | Required |
|------|-----------------------------------|----------|
| word | The word you want to find.        | Yes      |

### `.get_dictionary`
Get a list of tuples of all words in the dictionary.

### `.learn_file`
Learn a set of words from a piece of text in a file. If the file is found, all words it can interpret will be learned
by the dictionary. Otherwise, if the file wasn't found, a `FileNotFoundError`  will be thrown.

##### Parameters
| Name | Description                                          | Required |
|------|------------------------------------------------------|----------|
| text | The file containing the text that should be learned. | Yes      |

### `.learn_text`
Learn a set of words from a string of text.

##### Parameters
| Name | Description                                     | Required |
|------|-------------------------------------------------|----------|
| text | The text that should be learned.                | Yes      |

### `.learn_word`
Learn a new word given a string.

##### Parameters
| Name    | Description                                        | Required |
|---------|----------------------------------------------------|----------|
| word    | The word that should be learned by the dictionary. | Yes      |
| follows | A word that tends to follow the given word.        | No       |
| leads   | A word that tends to lead the given word.          | No       |