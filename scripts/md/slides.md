title: Agenda
class: big
build_lists: true

Things we'll cover:

- What is Sinon?
- Spies
- Stubs
- Mocks
- Fake Timers
- Fake XHR
- Fake Server
- Sandboxing
- Assertions
- Matchers

---

title: What is Sinon?
subtitle: 
class: segue dark nobackground

---

title: What is Sinon?
class: big
build_lists: true

- Comprehensive mocking library
- Standalone test spies, stubs and mocks for JavaScript
- No dependencies
- Works with any unit testing framework (qunit, jasmine, mocha, etc)
- Created by Christian Johansen
- Author of Test-Driven Javascript Development (http://tddjs.com)
- http://sinonjs.org

---

title: Sinon Spies
subtitle:
class: segue dark nobackground

---

title: Sinon Spies
class: big
build_lists: true

- Provide a test double for a single function
- Watch an existing method of an object

<pre class="prettyprint" data-lang="javascript">
var thing = {
  callCallback: function(cb) {
    cb();
  }
}

module( "Spies" );
test( "should spy on a callback", function() {
  var spy = sinon.spy();
  thing.callCallback(spy);
  ok(spy.called);
});
</pre>

---

title: Sinon Spies
class: big
build_lists: false

<iframe width="100%" height="490" style="width: 100%; height: 490px;" 
        src="http://jsfiddle.net/cavneb/4g4Kq/embedded/result,js,html/"
        allowfullscreen="allowfullscreen" frameborder="0"></iframe>

---

title: Sinon Spies
class: big
build_lists: false

<pre class="prettyprint" data-lang="javascript">
var thing = {
  callCallbackWithReturnValue: function(cb) {
    return cb();
  }
}
function realCallback() {
  return 4;
}

module( "Spies" );
test( "should call a real implementation if given a real function", function() {
  var spy = sinon.spy(realCallback);
  var returnValue = thing.callCallbackWithReturnValue(spy);
  ok(spy.called);
  ok(returnValue === 4);
});
</pre>

---

title: Sinon Spies
class: big
build_lists: false

<iframe src="/code_examples/spies-2.html" style="height: 490px;"></iframe>
<a class="open-test-btn" href="/code_examples/spies-2.html">open in new tab</a>

---

title: Sinon.js
subtitle: Subtitle
class: image

![Mobile vs desktop users](image.png)

---

title: Today
class: nobackground fill

![Many kinds of devices.](image.png)

<footer class="source">source: place source info here</footer>

---

title: Big Title Slide
class: title-slide

---

title: Code Example

Media Queries are sweet:

<pre class="prettyprint" data-lang="css">
@media screen and (max-width: 640px) {
  #sidebar { display: none; }
}
</pre>

---

title: Once more, with JavaScript

<pre class="prettyprint" data-lang="javascript">
function isSmall() {
  return window.matchMedia("(min-device-width: ???)").matches;
}

function hasTouch() {
  return Modernizr.touch;
}

function detectFormFactor() {
  var device = DESKTOP;
  if (hasTouch()) {
    device = isSmall() ? PHONE : TABLET;
  }
  return device;
}
</pre>

---

title: Centered content
content_class: flexbox vcenter

This content should be centered!
