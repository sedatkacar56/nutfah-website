Function factories? What is that? Is there such a thing? With one function, can I really create many other functions? I didn't believe it either. Yes — it's real. That's exactly why function factories exist. A function factory is a function that returns another function. Each returned function keeps its own settings.

One idea, two languages

JavaScript
function makeMultiplier(n) {
  return function(x) {
    return x * n;
  };
}

const double = makeMultiplier(2);
const triple = makeMultiplier(3);

double(4); // 8
triple(4); // 12

R
make_multiplier <- function(n) {
  function(x) {
    x * n
  }
}

double <- make_multiplier(2)
triple <- make_multiplier(3)

double(4) # 8
triple(4) # 12

➡️ Same concept, different syntax.
➡️ One factory → many specialized functions.

Takeaway

Sometimes programming isn't about learning something new — it's about realizing that what you've been using all along has a name.

#functionFactories #R #javaScript #goonlearning

39:6 "He created you from a single soul, then made from it its mate, and sent down for you eight pairs of livestock…"
