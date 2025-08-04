# General

## UI

[Streamlit](https://docs.streamlit.io/)

## Scripts

Add project path to .env file

```sh
echo $'\n'PROJECT_PATH=$PWD >> .env

```

## List appending

list.append() and list.extend() are both methods in Python used to add elements to the end of a list, but they differ in how they treat the elements being added.
list.append(element)
Adds the element as a single item to the end of the list.
If the element is an iterable (like a list, tuple, or string), it is added as a single nested item, not as individual elements.
The length of the list increases by 1.
Time complexity is O(1).
list.extend(iterable)
Adds each element of the iterable to the end of the list.
If the iterable is a string, each character is added as a separate element.
The length of the list increases by the number of elements in the iterable.
Time complexity is O(k), where k is the length of the iterable.

## Testing

### Pytest

https://realpython.com/pytest-python-testing/
