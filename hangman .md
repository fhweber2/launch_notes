  #!/usr/bin/ruby -w

    class Hangman
	def initialize(word)
		(@word = word).downcase!
		@progress = "_" * word.length
		@chances = 8
		@guessed = []
	end

	#Guess a letter in the secret word.
	#Hangman#progress will be modified to reflect the guessed letters.
	#Returns true if the letter is in the word, false otherwise
	#
	#params:
	#	letter => The letter being guessed -- a single character string
	#
	#exceptions:
	#	ArgumentError => if guess is not a single letter, or string
	def guess(letter)
		if letter.class.to_s != "String" or letter.length != 1
			raise ArgumentError, "Guess must be a single-character string!"
		else
			letter.downcase! #make sure letter is lower-case
			if @guessed.include? letter 
				raise ArgumentError, "Letter \"#{letter}\" was guessed already!"
			else
				@guessed << letter #add the letter to the list of guessed letters
				
				found = false
				(0...@word.length).zip(@word.scan(/\w/)) do |p, l| #enumerate each letter in the secret word
					if l == letter #if the letter matches...
						@progress[p] = l #...change @progress to reflect user's guess
						found = true #a match has been found
					end
				end
			end
			@chances -= 1 if !found #decrement the number of chances the user has left if a bad guess was made
			@guessed.sort!
			found #return true if a good guess, false otherwise
		end
	end

	#Check for a winner.
	#
	#Returns true if there is a winner, false otherwise.
	def winner?
		@progress == @word
	end

	#guessed letters.
	#
	#Returns a string of the previously guessed letters.
	def guessed
		@guessed.join(", ")
	end

	#Return the word as revealed by the player in a string. 
	#For example: "_ _ a _ _ t"
	def progress
		@progress.scan(/_|\w/).join(' ')
	end

	attr_reader :chances, :word
    end

    File.open("words.txt", 'r') do |f|
	words = []
	f.each { |w| words << w.gsub(/ /, '').chomp } #make sure word is free of spaces and trailing newline character removed
	
	h = Hangman.new(words[rand(words.length)]) #choose a random word
	
	while true
		begin
			break if h.winner? or h.chances < 0 #if the chances are up or there is a winner

			puts "\n#{h.progress.center(40)}"
			print "\n\nGuessed: ", h.guessed, "\n\n"
			puts "\nChances: #{h.chances}"
			print "\n\tEnter guess: "

			if h.guess(gets.chomp)
				puts "\nGreat guess!\n"
			else
				puts "\nOops! Bad guess.\n"
			end

			puts "_________________________________________________________________"
			sleep 1

		rescue
			puts "\n#{$!}\n" #print error message
			sleep 2
			retry
		end
	end

	if h.chances > - 1
		puts "\nGreat game! You guessed the word \"#{h.word}\"!"
	else
		puts "\nNo chances left! The word was \"#{h.word}\". Better luck next time."
		
______________


    def get_display(word)
      display =''
        for i in 0...word.length
            display = display +'-'
    end
    return display
    
    def is_letter_in_word(word,letter)
    if (word == nil)
        return false
    else
        if(word.index(letter)!=nil)
            return true
        else
            return false
        end
    end