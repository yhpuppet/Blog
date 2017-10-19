---
title: Custom UIViewController Transitions
date: 2017-10-18 23:18:05
tags:
---

# Custom UIViewController Transitions
Tired of pushing or pop UIViewController? Want to use custom transitions for UIViewController?
This can be done in iOS 7!
# Steps to build custom transitions
1. Trigger the transition either programmatically or via a segue.
2. UIKit asks the “to” view controller (the view controller to be shown) for its transitioning delegate. If it doesn’t have one, UIKIt uses the standard, built-in transition.
3. UIKit then asks the transitioning delegate for an animation controller via animationControllerForPresentedController(\_:presentingController:sourceController:). If this returns nil, the transition will use the default animation.
4. Once it has a valid animation controller, UIKit constructs the transitioning context.
5. UIKit then queries the duration of the animation using transitionDuration(\_:) from the animation controller.
6. Then UIKit invokes animateTransition(\_:) on the the animation controller to perform the transition.
7 .Finally, the animation controller calls the completeTransition(\_:) method on the transitioning context to indicate the animation is complete.
