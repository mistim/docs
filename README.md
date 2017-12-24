<!---
An Introduction to Elm
{:.origin_doc}
-->

# Введение в Elm

<!-- 
**Elm is a functional language that compiles to JavaScript.** It competes with projects like React as a tool for creating websites and web apps. Elm has a very strong emphasis on ч, ease-of-use, and quality tooling.
{:.origin_doc}
 -->

** Elm - это функциональный язык, который компилируется на JavaScript. ** Он конкурирует с такими проектами, как React, как инструмент для создания веб-сайтов и веб-приложений. Elm уделяет большое внимание простоте, простоте использования и качественной оснастке.

<!-- 
This guide will:

	- Teach you the fundamentals of programming in Elm.
  - Show you how to make interactive apps with *The Elm Architecture*.
  - Emphasize the principles and patterns that generalize to programming in any language.

{:.origin_doc} 
-->

Это руководство:

	- научит вас основам программирования в Elm.
	- покажит, как создавать интерактивные приложения с *The Elm Architecture*.
	- подчеркнит принципы и закономерности, которые обобщают программирование на любом языке.

<!-- 
By the end I hope you will not only be able to create great web apps in Elm, but also understand the core ideas and patterns that make Elm nice to use.
{:.origin_doc}
 -->

К концу я надеюсь, что вы не только сможете создавать отличные веб-приложения в Elm, но также бужете понимать основные идеи и шаблоны, которые делают Elm приятным в использовании.

<!-- 
If you are on the fence, I can safely guarantee that if you give Elm a shot and actually make a project in it, you will end up writing better JavaScript and React code. The ideas transfer pretty easily!
{:.origin_doc}
 -->

Если вы находитесь в раздумиях, я могу с уверенностью гарантировать, что если вы дадите Elm шанс и на самом деле сделаете проект в нем, вы в конечном итоге напишите лучший код JavaScript и React. Идеи переносятся довольно легко!

<!-- 
A Quick Sample
{:.origin_doc}
 -->

## Быстрый пример

<!-- 
Of course *I* think Elm is good, so look for yourself.
{:.origin_doc}
 -->

Конечно *Я* думаю, что Элм хорош, поэтому ищите себя.

<!-- 
Here is [a simple counter](http://elm-lang.org/examples/buttons). If you look at the code, it just lets you increment and decrement the counter:
{:.origin_doc}
 -->

Вот [простой счетчик] (http://elm-lang.org/examples/buttons). Если вы посмотрите на код, он просто позволяет вам увеличивать и уменьшать счетчик:

```elm
import Html exposing (Html, button, div, text)
import Html.Events exposing (onClick)

main =
  Html.beginnerProgram { model = 0, view = view, update = update }

type Msg = Increment | Decrement

update msg model =
  case msg of
    Increment ->
      model + 1

    Decrement ->
      model - 1

view model =
  div []
    [ button [ onClick Decrement ] [ text "-" ]
    , div [] [ text (toString model) ]
    , button [ onClick Increment ] [ text "+" ]
    ]
```

<!-- 
Notice that the `update` and `view` are entirely decoupled. You describe your HTML in a declarative way and Elm takes care of messing with the DOM.
{:.origin_doc}
 -->

Обратите внимание, что `update` и` view` полностью развязаны. Вы описываете свой HTML в декларативном ключе, и Elm заботится о том, чтобы возиться с DOM.

<!-- 
Why a *functional* language?
{:.origin_doc}
 -->

## Почему *функциональный* язык?

<!-- 
Forget what you have heard about functional programming. Fancy words, weird ideas, bad tooling. Barf. Elm is about:

  - No runtime errors in practice. No `null`. No `undefined` is not a function.
  - Friendly error messages that help you add features more quickly.
  - Well-architected code that *stays* well-architected as your app grows.
  - Automatically enforced semantic versioning for all Elm packages.

{:.origin_doc}
 -->

Забудьте о том, что вы слышали о функциональном программировании. Необычные слова, странные идеи, плохое оснащение. Буэээ. Об Elm:

   - на практике отсутствуют ошибки времени выполнения. Нет `null`. Нет `undefined` не является функцией.
   - дружественные сообщения об ошибках, которые помогут вам быстрее добавлять функционал.
   - хорошо продуманный код, который *остается* хорошо продуманным, так как ваше приложение растет.
   - автоматическое принудительное семантическое управление версиями для всех пакетов Elm.

<!-- 
No combination of JS libraries can ever give you this, yet it is all free and easy in Elm. Now these nice things are *only* possible because Elm builds upon 40+ years of work on typed functional languages. So Elm is a functional language because the practical benefits are worth the couple hours you'll spend reading this guide.
{:.origin_doc}
 -->

Никакая комбинация JS-библиотек никогда не сможет дать вам это, но в Elm все бесплатно и легко. Теперь эти приятные вещи возможны только потому, что Elm основывается на 40-летней работе на типизированных функциональных языках. Таким образом, Elm является функциональным языком, потому что практические выгоды стоят пару часов, которые вы потратите на чтение этого руководства.

<!-- 
I have put a huge emphasis on making Elm easy to learn and use, so all I ask is that you give Elm a shot and see what you think. I hope you will be pleasantly surprised!
{:.origin_doc}
 -->

Я приложил огромный акцент на том, чтобы Elm-у было легко учиться и использовать его, поэтому все, что я прошу, - это дать Elm шанс и посмотреть, что вы думаете. Надеюсь, вы будете приятно удивлены!