# Espresso Test! 🙂
![](https://miro.medium.com/max/568/1*_WLedJyydVmup2Sh3v2J5g.jpeg)

###  The Espresso test framework

Espresso is a testing framework for Android to make it easy to write reliable user interface tests.

Google released the Espresso framework in Oct. 2013. Since its 2.0 release Espresso is part of the Android Support Repository.

Espresso automatically synchronizes your test actions with the user interface of your application. The framework also ensures that your activity is started before the tests run. It also let the test wait until all observed background activities have finished.

It is intended to test a single application but can also be used to test across applications. If used for testing outside your application, you can only perform black box testing, as you cannot access the classes outside of your application.

Espresso has basically three components:

    ViewMatchers - allows to find view in the current view hierarchy

    ViewActions - allows to perform actions on the views

    ViewAssertions - allows to assert state of a view

The case construct for Espresso tests is the following:
Base Espresso Test

onView(ViewMatcher)       
 .perform(ViewAction)     
   .check(ViewAssertion); 

	- Finds the view
	- Performs an action on the view
	- Validates a assertioin

The following code demonstrates the usage of the Espresso test framework.

import static android.support.test.espresso.Espresso.onView;
import static android.support.test.espresso.action.ViewActions.click;
import static android.support.test.espresso.assertion.ViewAssertions.matches;
import static android.support.test.espresso.matcher.ViewMatchers.isDisplayed;
import static android.support.test.espresso.matcher.ViewMatchers.withId;

// image more code here...

// test statement
onView(withId(R.id.my_view))            // withId(R.id.my_view) is a ViewMatcher
        .perform(click())               // click() is a ViewAction
        .check(matches(isDisplayed())); // matches(isDisplayed()) is a ViewAssertion

// new test
onView(withId(R.id.greet_button))
.perform(click())
.check(matches(not(isEnabled()));

If Espresso does not find a view via the ViewMatcher, it includes the whole view hierarchy into the error message. That is useful for analyzing the problem.
