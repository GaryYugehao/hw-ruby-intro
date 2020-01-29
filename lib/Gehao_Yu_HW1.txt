# When done, submit this entire file to the autograder.

# Part 1

def sum arr
  # YOUR CODE HERE
  arr.inject(0, :+)
end

def max_2_sum arr
  # YOUR CODE HERE
  arr.sort!
  case arr.length
  when 0
    0
  when 1
    arr[-1]
  else
    arr[-1]+arr[-2]
  end
end

def sum_to_n? arr, n
  # YOUR CODE HERE
  for i in (0...arr.length)
	for j in (0...arr.length)
		if arr[j]==n-arr[i] and j!=i
			return true
		end
	end
  end
return false
end

# Part 2

def hello(name)
  # YOUR CODE HERE
  'Hello, ' + name
end

def starts_with_consonant? s
  # YOUR CODE HERE
  if s.start_with?('.','/','{','}',',','?',';',':','a','e','i','o','u','A','E','I','O','U','1','2','3','4','5','6','7','8','9','0','#','!','@','$','%','^','&','*','(',')') or s.length==0
    return false
  end
return true
end

def binary_multiple_of_4? s
  # YOUR CODE HERE
  s =~ /\A[0-9]+/ && s.to_i(2) % 4 == 0
end

# Part 3

class BookInStock
# YOUR CODE HERE
attr_accessor :isbn, :price
	def initialize(isbn, price)
		if isbn.to_s.empty? or price<=0
			raise ArgumentError
		end
		@isbn = isbn
		@price = price
	end

	def price_as_string
		    "$%.2f" % price
	end
end
