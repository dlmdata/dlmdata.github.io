---
layout: post
title: Curve Fitting by Linear Smoothing
---

Consider a nonlinear regression problem with a single predictor, \\( y_i = f(x_i)+\epsilon_i \\). Suppose we want to estimate the value of the regression function \\( y^* \\) at some new point \\( x^* \\), denoted \\( \hat f(x^* ) \\). A linear smoother estimates \\( \hat f(x^*) \\) by a linear combinate of

{% highlight r %}

smooth <- function(x, y, kernel, bw){
  predict <- function(z){ w <- kernel((x-z)/bw)/bw; w %*% y / sum(w) }
  result <- list(x=x, y=y, kernel=kernel, bw=bw, predict=Vectorize(predict))
  invisible(structure(result, class="smooth"))
}

{% endhighlight %}
