Refer back to the Railscast:


<https://github.com/railscasts/287-presenters-from-scratch>

<http://railscasts.com/episodes/287-presenters-from-scratch>


<https://github.com/railscasts/287-presenters-from-scratch>


Presenter Pattern - take an ActiveRecord object and translate it to a view context.

To:

Hide Info (users, model - keep info confidential info)
Formattting
 
Gem:  Draper (Intended to be a One-to-One relationship between a helper & model)

<https://github.com/drapergem/draper>

create a feature branch

    git checkout -b <something>  # then

    rails g decorator review
    
FYI: 

    #seg fault  
    rvm use 1.9.3@something_app
    
Features Test:

    require spec_helper
        
        describe ReviewDecorator do
            context  'formatted display' do
                let(:review) do
                 FactoryGirl.create(:review)
                end
                
                let(:decorate_review) do
                    review.decorate
                end
                
            it 'shows a rating' do
                expect(decorator_review.formatted_display)
                to include(review.rating.to_s)
            end
            
            it 'shows the body of the review' do
                expect
                
                
__________

    h.simple_format(content)
    
    # a way to implement a  way to style html in rails
    
__________

    class ReviewDecorator < Draper::Decorator
        delegate_all
            
        def rating_header
          h.content_tag(:strong) do
            rating.to_s
        end
            
        def formatted_content
          h.simple_format(content)
        end
        
        def formatted_display
          rating_header + formatted_content
        end
    end
_________    
    
    # now modify the Controller to decorate the View 

_________

RSPEC (shared behaviors - google it)

    # here's some really advanced stuff!
    
    Review.joins("INNER JOIN likes ON
        reviews.id = likes.likeable_id AND
        reviews.likeable_type = 'Review'")
        
   # adding a 'counter cache' on the has_many (look at the documentation) 
   
   
