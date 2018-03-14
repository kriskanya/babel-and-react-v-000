# Babel and React

## Overview

In this lesson, we'll unpack what **Babel** brings to the table when developing React applications.

## Objectives

1. Learn what Babel is
2. Learn how Babel integrates with React
3. Frame Babel's relative importance at this stage in learning React

# Babel

![Tower of Babel](http://www.ancient-origins.net/sites/default/files/field/image/tower-of-babel-2.jpg)

If you don't have time to procrastinate and [read the wiki][origin-myth], and want to get on with learning programming, allow us to provide the [TL;DR][TL;DR] and why it is relevant to the Babel tool we use:

The Tower of Babel was a colossal construction project long ago. It was being built by a united humanity speaking the same language, with the intention of reaching such heights that heaven itself could be accessed. While it was being constructed, the God in the story, (for debated reasons), afflicted the united humans by confounding their speech. This ensured the once united humanity could no longer communicate.<sup>1</sup>

Babel, ([the one we use][babel]), seeks to do the opposite of the aforementioned affliction: it turns many languages/syntaxes/versions into one! As you may already know, JavaScript (based on the ECMAScript [ES] standard) is an evolving language. Over time we have had several iterations. For the most part, ECMAScript's evolution has changed to incorporate more features and language constructs over time (think ES6 arrow functions, class syntax, `let`, and `const` vs. their absence in ES5!).

Babel most notably gained popularity because it [compiled/transpiled][transpile-compile] newer ES6 syntax and language features into the older ES5. This was especially important when ES6 came out because many browsers had not yet updated their JavaScript engines to interpret the new language features of ES6.

As of 2018, you are in less danger of your target browsers not implementing ES6 syntax than before.<sup>2</sup> For example, open up your browser's developer console and attempt to assign `let y = 4; console.log(y)`. Better believe Chrome Boi won't complain!

<p align="center">
  <img src='https://learn-verified.s3.amazonaws.com/chrome-boi-wont-complain.png' height=500 width=300/>
</p>

#### Then why is Babel important?

> "To Babel or not to Babel: ay, there's the rub"  
> &nbsp;&nbsp;&nbsp;&nbsp;&#8211; _William Shakespear's Hamlet[hamlet]_

<!-- TODO: instead provoke question "then why do we want to use babel still" here and answer here, then show how its particularly useful for JSX. babel used for synchronization, using new features, via code transformation -->

Even though most major browsers are up to date with the current ECMAScript features, Babel is still useful when creating web application, especially so in React. Babel turns JSX into React function calls. That is, **Babel turns JSX into normal JavaScript written with the React library**.

Enough theory! Let's see it in action:

```JavaScript
var profile = (
  <div>
    <img src="avatar.png" className="profile" />
    <h3>{[user.firstName, user.lastName].join(' ')}</h3>
  </div>;  
)
```

...when the above is run through Babel, we receive:

```JavaScript
var profile = (
  React.createElement("div", null,
  React.createElement("img", { src: "avatar.png", className: "profile" }),
  React.createElement("h3", null, [user.firstName, user.lastName].join(" ")))
);
```

While you don't need Babel as a dependency when writing React code, it means you have to write in the non-JSX syntax seen in the output above. For now, we will be teaching and writing with the pre-babel-compiled (first syntax above) JSX in our React applications.

#### Not Just For JSX

In addition to the JSX magic it provides, Babel can also compile other features and syntactic sugar that is not yet, or never will be, a part of ECMAScript! One example of this is a babel plugin that enables the usage of [language features proposed for ECMAScript, but not yet implemented][babel-stage-2].

#### We must go deeper!

No way! _we mustn't_! _we shouldn't_! _we couldn't!_ But If you _need_ know more about how React incorporates Babel, feel free to run [`npm run eject`][eject] _at your own risk_ in this repository (which was made with `create-react-app`). For the most part, we will be using the handy `create-react-app` when initializing new React projects, which obfuscates pre-configured files from us for user-friendliness and to avoid boiler-plate code. `npm run eject` will undo that obfuscation, and expose you to these pre-built configurations (read: "world of hurt"). For now, we recommend staying focused on improving your high-level React development skills, and leaving the general project configuration up to React.

<p align="center">
  <img src='https://learn-verified.s3.amazonaws.com/npm-run-eject.jpeg' height=500 width=300/>
</p>

---

## Summary

You have just been introduced to a tool you likely have not worked directly with before. Luckily, its straight forward to summarize:

**Babel** enables us to use syntax that browsers won't natively recognize by **pre-compiling** it into syntax that browsers _do_ natively recognize. When used with React, this can (and in our case will) include, but not be limited to, digesting JSX.

## Looking Forward

That was a chunk of new information, and we have even more coming up. If this is your first time being exposed to a tool like Babel, treat yourself. Stand up, stretch your legs, look at a real human that's not in meme format: you deserve it. When you come back, we will get started on **Webpack** in the following lesson.

## Resources
- [Babel]: http://babeljs.io/

<p class='util--hide'>View <a href='https://learn.co/lessons/babel-and-react'>Babel and React</a> on Learn.co and start learning to code for free.</p>

<sup>1</sup> Before you have any epiphanies on us, this is most likely _not_ where the term "babbling" comes from  
<sup>2</sup> When 'in the field', so to speak, backwards compatibility will be more important

[origin-myth]: https://en.wikipedia.org/wiki/Tower_of_Babel
[TL;DR]: https://en.wikipedia.org/wiki/TL;DR
[babel]: http://babeljs.io/
[transpile-compile]: https://stackoverflow.com/questions/43968748/is-babel-a-compiler-or-transpiler
[chrome-boi]: https://learn-verified.s3.amazonaws.com/chrome-boi-wont-complain.png
[hamlet]: https://en.wikipedia.org/wiki/To_be,_or_not_to_be#Text
[babel-stage-2]: https://babeljs.io/docs/plugins/preset-stage-2/
[eject]: https://github.com/facebook/create-react-app/blob/master/packages/react-scripts/template/README.md#npm-run-eject
[browserify]: http://browserify.org/
[syntactic-sugar]: https://en.wikipedia.org/wiki/Syntactic_sugar
[swol]: https://scontent.cdninstagram.com/t51.2885-15/s640x640/sh0.08/e35/13109122_818162874981972_854250567_n.jpg?ig_cache_key=MTI0MDEwMTQwNDQ5MDUyOTM2MQ%3D%3D.2.l
[hydrofoil]:https://www.google.com/search?q=hydrofoil+catamaran&source=lnms&tbm=isch&sa=X&ved=0ahUKEwia5Yyls-rZAhWIjVkKHdd-A3MQ_AUICygC&biw=1280&bih=659#imgrc=JhI18wkkvwakwM:
[they-fly]:https://www.youtube.com/watch?v=a49jy9ba4FQ&t=06m