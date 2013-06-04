#Methods 

    class QuestionAnswerPair
        attr_accessors :question, :answers
        
        def
            puts question 
            gets.chomp
        end
            
    end
        
        def valid?(response)
        self.answer == response
                
        end
            
    qa = QuestionAnswerPair.new
    qa question = "What is your fav.."  #setter
    qa.question                         #getter
    qa.answer = "green"                 #setter
    user_response = qa.ask              #blue
    qa.valid?(user_resp)




"?" returns the value as T/F

**self is a reference to the instance

Noun 
            
            class

Property

            attr_accessors

Verbs

            methods
            
            
##Constructors

        class QuestionAnswerPair
        
    def initialize(question, answer)       #constructor
        @question = question
        @answer = answer
    end
                
    def
        puts @question 
        gets.chomp
    end
                
    def valid?(response)
        @answer == response
                  
        end   
    end  
                
                
    qa = QuestionAnswerPair.new (Favorite Color? , ""Green')
    qa.collection [ ]
    qa.collection << 99 
    
#Attributes
        
    attr_writer
    attr_reader
                
            attr_reader(q,a)
                        
                def initialize(q,a)
                

###note : a method definition where the name is preceded by:
    self. is known as a class method,
and a method 
without self. is called an instance method

        
        
        