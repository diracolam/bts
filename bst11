class Node
	@value = nil
	@left = nil
	@right = nil

	def initialize(value)	
		@value = value
	end

	def setLeft(left)
		@left = left
	end
		
	def setRight(right)
		@right = right
	end

	def left
		@left
	end

	def right
		@right
	end

	def getValue
		@value
	end

	def to_s
	  "(#{@value})"
	end
end

class Tree
	@root = nil

	def initialize(ar)	
		@root = buildTree(ar)
	end
	
	def buildTree(ar)
		ar = ar.sort
		ar = ar.uniq

		if (ar.size < 1)
		  return nil
		elsif (ar.size == 1)
		  return Node.new(ar[0])
		elsif (ar.size == 2)
		  n1 = Node.new(ar[0])
		  n2 = Node.new(ar[1])
		  n2.setLeft(n1)
		  return n2
		elsif (ar.size == 3)
		  r = Node.new(ar[1])
		  r.setLeft(Node.new(ar[0]))
		  r.setRight(Node.new(ar[2]))
		  return r
		end
		
		mid = (ar.size)/2
		root = Node.new(ar[mid])

		root.setLeft(buildTree(ar[0...mid]))
		root.setRight(buildTree(ar[mid+1..-1]))

		return root
	end
	
	def size
	  count = 0
	  q = [@root]
		while (q.size > 0)
		  n = q.shift
		  if (!n.nil?)
			count += 1
		    q << n.left
			q << n.right
		  end
		end
       return count
	end

	

	def to_s
		q = [@root]
		r = ''
		count = 0
		line = 0
		total_layers = (Math.log(size,2)+1).to_i
		space = 4 * (2**(total_layers -1)) / 2 - 2
		r += space.times.map{' '}.join
		while (q.size > 0)
		  n = q.shift
		  r += " #{n}"
		  count+=1
		  if (count == 2**line)
			r += "\n"
			space /= 2
			line+=1
			count=0
		  end
          r += space.times.map{' '}.join
		  if (!n.nil?)
		    q << n.left
			q << n.right
		  end
		end
		return r
	end
end

t = Tree.new([1,3,5,8,6,4,2,3,0,8,2])
puts t
t.delete(3)

