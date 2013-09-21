Refactoring Ruby Edition, Chapter 1
===============

BEWARE of two errors in the first
chapter of the book ... 

1)
==

this is WRONG:

  case @price_code
  when REGULAR : RegularPrice.new
  when NEW_RELEASE : NewReleasePrice.new
  when CHILDRENS : ChildrensPrice.new
  end

it should be:

  case @price_code
  when REGULAR then RegularPrice.new
  when NEW_RELEASE then NewReleasePrice.new
  when CHILDRENS then ChildrensPrice.new
  end

The syntax when ... : was never officially part of ruby
and was removed in one of the recent versions

2)
==

module DefaultPrice
end

import Price  # <-- should be DefaultPrice also
