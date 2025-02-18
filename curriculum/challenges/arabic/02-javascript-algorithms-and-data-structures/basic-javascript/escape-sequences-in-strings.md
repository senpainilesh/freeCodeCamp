---
id: 56533eb9ac21ba0edf2244b6
title: تسلسلات الهروب في المقاطع (Escape Sequences in Strings)
challengeType: 1
videoUrl: 'https://scrimba.com/c/cvmqRh6'
forumTopicId: 17567
dashedName: escape-sequences-in-strings
---

# --description--

الاقتباسات (Quotes) ليست الرموز الوحيدة التي يمكن أن تكتب <dfn>باحتياليه</dfn> داخل المقطع (string). وهناك سببان لاستخدام رموز احتيالية (escaping characters):

1.  للسماح لك باستخدام الرموز التي قد لا تتمكن من استخدامها، مثل سطر جديد (newline).
2.  للسماح لك بتمثيل الاقتباسات (Quotes) متعددة في مقطع دون أن يسيء JavaScript فهم ما تعنيه.

وقد تعلمنا ذلك في التحدي السابق.

<table class='table table-striped'><thead><tr><th>الكود</th><th>الناتج</th></tr></thead><tbody><tr><td><code>\'</code></td><td>single quote</td></tr><tr><td><code>\"</code></td><td>double quote</td></tr><tr><td><code>\\</code></td><td>backslash</td></tr><tr><td><code>\n</code></td><td>newline</td></tr><tr><td><code>\t</code></td><td>مساحة يختارها المستخدم (tab)</td></tr><tr><td><code>\r</code></td><td>إعادة التنقل إلى أول السطر (carriage return)</td></tr><tr><td><code>\b</code></td><td>word boundary</td></tr><tr><td><code>\f</code></td><td>form feed</td></tr></tbody></table>

*لاحظ أن يجب أن تكون الخط المائل (backslash) نفسه أحتيالي (escaped) ليتم عرضها كخط مائل backslash.*

# --instructions--

عيّن الأسطر الثلاثة التالية من النص في المتغير `myStr` الوحيد باستخدام تسلسل احتيالي (escape sequences).

<blockquote>FirstLine<br>    \SecondLine<br>ThirdLine</blockquote>

سوف تحتاج إلى استخدام تسلسل احتيالي لإدراج الرموز الخاصة (special characters) بشكل صحيح. ستحتاج أيضًا إلى اتباع التباعد كما هو موضح أعلاه، دون مسافات بين التسلسل الاحتيالي escape sequences أو الكلمات.

**ملاحظة:** يتم الحصول على التباعد (indentation) في `SecondLine` باستخدام رمز التحايل الشريط (tab escape character) وليس المسافة الفارغة (space).

# --hints--

يجب ألا يحتوي `myStr` على أي مسافات

```js
assert(!/ /.test(myStr));
```

يجب أن يحتوي `myStr` على المقطع (string) الآتي `FirstLine`, و `SecondLine`, و `ThirdLine` (تذكر الحساسية حالة الحرف (case sensitivity))

```js
assert(
  /FirstLine/.test(myStr) && /SecondLine/.test(myStr) && /ThirdLine/.test(myStr)
);
```

يجب أن يتبع `FirstLine` رمز السطر الجديد (newline character) الاتي `\n`

```js
assert(/FirstLine\n/.test(myStr));
```

يجب أن يحتوي `myStr` على رمز الشريط (tab character) وهو `\t` الذي يتبع رمز السطر الجديد (newline character)

```js
assert(/\n\t/.test(myStr));
```

يجب أن يسبق `SecondLine` رمز خط مائل (backslash character) يكتب هكذا `\`

```js
assert(/\\SecondLine/.test(myStr));
```

يجب أن يكون هناك رمز السطر الجديد (newline character) بين `SecondLine` و `ThirdLine`

```js
assert(/SecondLine\nThirdLine/.test(myStr));
```

يجب أن يحتوي `myStr` فقط على الرموز التي تظهر في التعليمات

```js
assert(myStr === 'FirstLine\n\t\\SecondLine\nThirdLine');
```

# --seed--

## --seed-contents--

```js
const myStr = ""; // Change this line
```

# --solutions--

```js
const myStr = "FirstLine\n\t\\SecondLine\nThirdLine";
```
