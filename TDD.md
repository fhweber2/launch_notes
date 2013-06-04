##Test Driven Design


###1.  Start w/ a failing test

###2.  Write the simplest code to make the test pass

###3. Refactor

###4. Repeat

Newly Pair

    gem install rspec
       
Test/Unit

mintiest (new to Rails)     

    touch question_answer_pair.rb
    require 'rspec'
    
    require_relative 'question_answer_pair'
    class QuestionAnswerPair
    
    describe QuestionAnswerPair do
        it 'has a question' do
            expect(QuestionAnswerPair.new.question).to_not be_nill  
    end

Condition #1 Passed

Next Step - Write the simplest code to make the test pass
    "back to the file and write another question method"

    class QuestionAnswerPair
       describe QuestionAnswerPair do 
        it 'has a questions do 
            pair - QuestionAnswerPair.new 
            expect(pair.question).to_not be_nil
        end
    end  
    
spec --color (in the file) - outputs code to 'green' 


###**Test contains a Behavior and an Expectation


    it 'has a sensical question' do
    
    q = 'What is your favorite color?'
    pair = QuestionAnswerPair.new
    expect(pair.question).to eql(q)

----

    class QuestionAnswerPair (question)
        @question = question 
    end
    
     def question 
      @question
      end
    end
    
####Let's get a Green Test

    it 'has a sensical answer'  do 
        a = QuestionAnswerPair.
        new(' a question', a )
        expect(pair.answer).to eql(a)
        end
    end


Now go back and change the other tests to 
    