#Conway's Game of Life
# 
#  1. Any live cell with fewer than two live neighbours dies, as if caused by under-population.
#  2. Any live cell with two or three live neighbours lives on to the next generation.
#  3. Any live cell with more than three live neighbours dies, as if by overcrowding.
#  4. Any dead cell with exactly three live neighbours becomes a live cell, as if by reproduction.

#puts "Enter number of rows for world"
#x = gets.chomp
#puts "Enter number of columns for world"
#y = gets.chomp

#@world = World.new x, y

#while @world.creatures.size > 0
#	tick()
#end

class Game
	def tick

	end

	def draw

	end
end

class Cell
	attr_reader :x, :y
	def initialize world, x, y
		world.checkBounds x,y
		@x = x
		@y = y	
		world.creatures <<  self
	end

	def neighbor_count world
		i=-1
		count = 0
		while i <= 1 do
			j = -1
			while j<=1 do
				unless (i == 0 && j == 0) 
					if (world.hasLivingCreature?(self.x + i, self.y + j))
						count += 1
					end
				end
				j += 1
			end
			i += 1
		end

		return count	
	end
end

class World
	attr_reader :plots, :creatures		
	def initialize gridCountX, gridCountY
		@gridCountX = gridCountX
		@gridCountY = gridCountY
		@plots = Array.new gridCountX*gridCountY	
		@creatures = []
	end

	def createCreatures amount
		amount.times {
			Cell.new(self, rand(@gridCountX), rand(@gridCountY))
		}
	end
	
	#Think through how to get errors....Maybe place a prompt for value within the Bounds, Consider immediately killing 
	#the cell since this is what happens if normal cells exist the board
	def checkBounds x, y
		if (x > @gridCountX || y > @gridCountY)
			exit 1
		end
	end

	def hasLivingCreature? x, y
		@creatures.each { |creature|
			if (creature.x == x && creature.y == y) 
				return true
			end

		}
		return false
	end

end
