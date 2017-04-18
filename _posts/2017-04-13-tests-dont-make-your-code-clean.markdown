---
layout: post
title:  "Test != Quality"
date:   2017-04-13 14:42:51 +0100
categories: apprenticeship
---
![photo pen]({{ site.url }}/assets/pen.jpg)
Testing has many benefits on your software, I thought "software quality" was one of them for a long time. It is true that unit tests encourage you to modularize your code and document it, but
it doesn't check the quality of your code.

For example, although this piece of code has "100%" test coverage, the code is bad in many ways.

``` ruby
class MathHelper
  def calculFactorial(x)
    return  1 if x == 0

     x * self.calculFactorial(x - 1)

 end
end

 RSpec.describe do
   it "tests the function" do
     expect(MathHelper.new().calculFactorial(3)).to eq(6)
   end
 end
```

The code is inconsistent: it doesn't follow any guidelines, has terrible naming, and is way more complicated compared to this one:

``` ruby
class Factorial
  def self.for(number)
    return 1 if number == 0

    number * self.for(number - 1)
  end
end

RSpec.describe do
  it "returns 6 when factorial of 3" do
    expect(Factorial.for(3)).to eq(6)
  end
end
```

With this example, we can see that the quality of a code isn't related to the tests. The tests can't guaranty that your team follow the same guideline or if your code is consistent. The tests can't know if your colleagues will understand your code; the test cannot check you coded with intention nor that you have selected the most appropriate names.  

The issues that cannot be checked by your tests and that are not checked by you will increase the technical debt of your software. This is why, it's important to know that is not the role of your tests to check the quality of a code but yours and your pairs. 

But don't get me wrong, it's difficult to develop anything of quality without tests.


