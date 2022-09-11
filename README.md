[![cover](images/cover.png)](SUMMARY.md)

## 이 책에 관하여

이 책은 일반적인 함수형 패러다임에 관한 책입니다. 우리는 세계에서 제일 유명한 함수형 프로그래밍 언어인 'JavaScript'를 사용할 겁니다. 몇몇은 현재의 JavaScript 문화가 주로 명령형 패러다임이 지배적이기 때문에, 잘못된 선택이라고 느낄지도 모르겠습니다. 그럼에도 불구하고, 저는 이러한 이유들 때문에 JavaScript를 사용하는 것이 FP를 배우는 데에 꽤 좋은 선택이라고 믿습니다:

 * **당신은 아마도 JavaScript를 매일 업무에서 사용하고 있을겁니다.**

    이게 당신으로 하여금 이 책에서 배운 것들을 밤이나 주말에 소수의 사람들만 이해할 수 있는 유니크한 함수형 프로그래밍 언어로 토이 프로젝트에 적용해보는 대신, 당신의 기존 지식을 활용해서 매일같이 실제 업무에서 적용하고 연습해볼 수 있게 만들어줍니다. 


 * **프로그램 작성을 시작하기 위해서 모든 걸 처음부터 배우지 않아도 됩니다.**

    순수 함수형 언어에서는, `monad`의 도움 없이 변수를 로깅해보거나 DOM 노드를 읽을 수 없습니다. 하지만 JavaScript에서는 우리가 어려움 없이 이런 기능들을 사용할 수 있습니다. 또한 여러가지 패러다임을 혼합해서 동시에 지원하기 때문에, 함수형 패러다임을 연습하다가 어려움을 겪을경우 그 부분만 선택적으로 기존 패러다임을 활용해서 문제를 해결할 수 있기때문에 부담이 적습니다.


 * **JavaScript는 최상급 함수형 코드를 작성하기 위한 모든 것을 제공합니다.**

    JavaScript는 작은 라이브러리 한 두개정도의 도움만 받으면 Scala나 Haskell같은 언어의 모든 기능을 따라할 수 있습니다. 지금은 객체 지향 프로그래밍이 업계를 점령해버렸지만, JavaScript 에서의 객체 지향은 분명히 좀 어색합니다. 마치 고속도로에서 캠핑을 하거나 장화를 신고 탭댄스를 하는것 같달까요. 우리가 모르는 사이에 `this`가 바뀌지 않도록 `bind`를 온갖 곳에서 사용해야 하고, `new` 키워드를 빼먹은 경우 발생하는 이상한 동작을 막기 위해 여러 방어코드를 만들기도 하고, `private` 멤버는 closure를 통해서만 가능하기도 합니다. 여러분들 중 대다수에게는 함수형 프로그래밍이 더 자연스럽게 느껴질거에요. 

이렇게 말하기는 했지만, 정적 타입 함수형 언어가 이 책에서 설명하는 스타일로 코딩하기에 완벽한 환경이라는 데에는 의심의 여지가 없다. JavaScript는 이 패러다임을 배우는 수단으로써 우리에게 의미가 있고, 어떤 언어로 적용할지는 전적으로 당신에게 달려있다. 운 좋게도, 이 패러다임은 수학적이고, 그렇기 때문에 어떤 언어에서든 통할 수 있다. 수학적으로 준비된 환경이라면 Haskell, PureScript, Scala 를 막론하고 마치 집에 온것처럼 편안하게 함수형 패러다임을 적용하는 자신을 발견할 수 있을 것이다.    



## Gitbook에서 읽어보세요

최적의 가독성을 위해서, [Gitbook을 통해 읽어보세요](https://soomgo-public.gitbook.io/mostly-adequate-guide-ko/).

- Quick-access side-bar
- In-browser exercises
- In-depth examples


## 코드를 통해 놀아보세요

To make the training efficient and not get too bored while I am telling you another story, make sure to play around with the concepts introduced in this book. Some can be tricky to catch at first and are better understood by getting your hands dirty.
All functions and algebraic data-structures presented in the book are gathered in the appendixes. The corresponding code is also available as an npm module:

```bash
$ npm i @mostly-adequate/support
```

Alternatively, exercises of each chapter are runnable and can be completed in your editor! For example, complete the `exercise_*.js` in `exercises/ch04` and then run:

```bash
$ npm run ch04
```

## Download it

Find pre-generated **PDF** and **EPUB** as [build artifacts of the latest release](https://github.com/MostlyAdequate/mostly-adequate-guide/releases/latest).

## Do it yourself

> ⚠️ This project setup is now a bit old and thus, you may run into various issues when building this locally. We recommend to use node v10.22.1 and the latest version of Calibre if possible. 

```
git clone https://github.com/MostlyAdequate/mostly-adequate-guide.git
cd mostly-adequate-guide/
npm install
npm run setup
npm run generate-pdf
npm run generate-epub
```

> Note! To generate the ebook version you will need to install `ebook-convert`. [Installation instructions](https://gitbookio.gitbooks.io/documentation/content/build/ebookconvert.html).

# Table of Contents

See [SUMMARY.md](SUMMARY.md)

### Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md)

### Translations

See [TRANSLATIONS.md](TRANSLATIONS.md)

### FAQ

See [FAQ.md](FAQ.md)



# 로드맵

* **파트 1** (챕터 1-7) 은 이 가이드의 기초입니다.
* **파트 2** (챕터 8-13) 펑터(functor), 모나드(monad) 등 traversable로 이어지는 모든 타입 클래스를 설명합니다. 제가 변환기(transformer)나 순수 어플리케이션(pure application)에 대해 설명할 수 있기를 바랍니다. 
* **파트 3** (챕터 14+) will start to dance the fine line between practical programming and academic absurdity. We'll look at comonads, f-algebras, free monads, yoneda, and other categorical constructs.


---


<p align="center">
  <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">
    <img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" />
  </a>
  <br />
  This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Attribution-ShareAlike 4.0 International License</a>.
</p>
