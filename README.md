![App Brewery Banner](https://github.com/londonappbrewery/Images/blob/master/AppBreweryBanner.png)


# Destini 🤔

## Our Goal

In this challenge, you will be building a choose your own adventure game like Bandersnatch. In the process, you should apply your knowledge from the last module (Quizzler) to use Dart OOP principles to build a well organised project.

![Finished App](https://github.com/londonappbrewery/Images/blob/master/Destini.gif)


>This is a companion project to The App Brewery's Complete Flutter Development Bootcamp, check out the full course at [www.appbrewery.co](https://www.appbrewery.co/)

![End Banner](https://github.com/londonappbrewery/Images/blob/master/readme-end-banner.png)

## Notes
- If clauses can be replaced by 
`[boolean clause] ? [if true] : [if false]`
- story_brain.dart 
`bool buttonShouldBeVisible(){...}` 
method can be made into a single line by 
`bool buttonShouldBeVisible() => _storyNumber < 3;`
- `void nextStory(int choiceNumber){if clauses...}` can be effectively replaced by using maps as follows:
```
  Map<int, Map<int, int>> choices = {
    0: {1: 2, 2: 1},
    2: {1: 5, 2: 4},
    1: {1: 2, 2: 3},
  };
  List<int> endStoriesBranch = [3, 4, 5];
  void nextStory(int choiceNumber) {
    if (endStoriesBranch.contains(_storyNumber)) {
      reset();
      print('end of the story');
    } else {
      _storyNumber = this.choices[_storyNumber][choiceNumber];
    }
    print('User choosen $choiceNumber redirecting to story $_storyNumber');
  }
  ```