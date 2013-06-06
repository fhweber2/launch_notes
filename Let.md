From StackOverflow:

http://stackoverflow.com/questions/5359558/when-to-use-rspec-let/5359979#5359979

####I always prefer -let- to an instance variable for a couple of reasons:

•	Instance variables spring into existence when referenced. This means that if you fat finger the spelling of the instance variable, a new one will be created and initialized to nil, which can lead to subtle bugs and false positives. Since let creates a method, you'll get a NameError when you misspell it, which I find preferable. It makes it easier to refactor specs, too.

•	A before(:each) hook will run before each example, even if the example doesn't use any of the instance variables defined in the hook. This isn't usually a big deal, but if the setup of the instance variable takes a long time, then you're wasting cycles. For the method defined by let, the initialization code only runs if the example calls it.

•	You can refactor from a local variable in an example directly into a let without changing the referencing syntax in the example. If you refactor to an instance variable, you have to change how you reference the object in the example (e.g. add an @).

•	This is a bit subjective, but as Mike Lewis pointed out, I think it makes the spec easier to read. I like the organization of defining all my dependent objects with let and keeping my it block nice and short.

####A Good Test from:  www.betterspecs.com

    describe '#type_id' do
        let(:resource) { FactoryGirl.create :device }
         let(:type)     { Type.find resource.type_id }

         it 'sets the type_id field' do
        resource.type_id.should == type.id
        end
    end