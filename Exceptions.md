#Exceptions 

        def self.create_from_input
            puts "What is the answer?"
            question = gets.chomp
            
            puts "What is the answer?"
            answer = gets.chomp
            self.new(question, answer)
        end
        
        