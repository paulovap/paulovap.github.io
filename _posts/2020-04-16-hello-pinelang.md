---
layout: post
title: Pinelang, hello world!
subtitle: A script language on top of Kotlin
gh-repo: paulovap/pinelang
gh-badge: [star, fork, follow]
bigimg: /img/tree_bg.jpg
tags: [pinelang, script, kotlin]
comments: true
---

So I decided to resurrect an old project of mine to create a small footprint scripting language on top of Kotlin. But why would one do that?

```qml
  HttpServer {
    hostname: 'localhost'
    port: 8080
    on connection: (resp) { println("Hello world:" + resp.text) }
  }
```

## What is Pinelang?

PineLang is a minimalistic, **reactive**, **declarative** scripting language to be embedded on **Kotlin** applications, with the objective of enabling a dynamic, runtime, representation of the tree-like hierarchy of objects in Kotlin.

Think of it, as a way to provide more dynamism to a compile-time language like Kotlin.

## Why use Pinelang?
You shouldn't. 

This is a pet project with the main goal being my personal learning about Kotlin, programming languages, interpreters, syntax-tree and the other computer-science related topics. Hopefully, something useful will come out. But this is not a promise.

The decision to use Kotlin as the foundation is pretty straightforward and for selfish reasons. I am an Android developer and I need to master this new language adopted by Android. Aside from that, I wanted to learn more about computer science techniques that could leverage more dynamism to native mobile Apps, so development could be simplified, maybe, if some success with the horizon, expand the core language do new platforms.

I took a heavy inspiration for scripting languages/frameworks on the market, like Reactive-Native, Flutter, QML and decided to build my own.

## Goals and desired features

Basically the goal is:

* Make simple to expose Kotlin objects to script
* No dependencies to Kotlin-specific platform that is running into
* No code generation
* Performance over features
* Minimum ovehead
* Strong tooling support


## Use cases

The use-cases that Pinelang fits best is: Configuration file, UI development.

Example:

{% highlight qml linenos %}
Program {

  Page {
    id: main
    visible: !about.visible
    header: ActionBar {
      title: "My awesome App"
      Action { text: "About"; on click: about.visible = true }
    }
    body: Card {
      title: "This is a new card"
      content: "Maybe we can have some <b>HTML<b/> tags here"
    }
  }

  Page {
    id: about
    visible: false
    header: ActionBar { title: "About the App" }
    body: Card {
      content: "My awesome App version ${Globals.Version}"
    }
  }
}
{% endhighlight %}

## Conclusion
In the upcoming posts, I will lay down more information about the implementation details. Looking into 
most of the challenges of building DSLs and toolings that provide support on this task.
