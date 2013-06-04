###Matchers


    expect(true).to be_true
    
    expect('foo').to  eql('foo')
    
    expect(1).to  be > 0
    
    
________

###Assertions

    describe Book do
    
        it 'has a title' do
            book = Book.new(title: 'PS')
            
    expect(book.title).to  sql('PS')
    
    
    it 'has a description'
    
______________________
    
    
With an Instance Variable 

    require 'rspec'
    
    describe Book do
    
       before(:each) do
           @book = Book.new(title: 'PS')
    end     
    
    
    it 'has a description' do
        expect (@book.description).to_not be_nil
        
    end

______________

###Right (are my results right )

###B -  boundary conditions sensible

###I -  inverse relationship

###C - Cross Check Results

###E - Error Condition

###P - Performance in boundary
    