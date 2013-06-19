###Seed a DB

1st thing is to write the spec

Make the file in the /lib directory 

Place the MenuItem in the /ib

    describe Seeder::MenuItems do
      let (:seeder) {Seeders::MenuItems}
    
         it 'seeds menu items' do
            menu_item_ount = MenuItem.count
            seeder.seed
            expect(MenuItem.count).to_not eq(menu_item_count)
        end
    
        it 'seeds ingredients associated with menu items'
            seeder.seed
            expect(MenuItem.first.ingredients).to_not be eq()
        it 'can be run multiple times without duplication'
    end

gem 'faker'  creates fake data to run your tests

    module Seeders
        module MenuItems
            class << self
                def seed
                    menu_items.each do |name, array|
                        item = MenuItems.new
                        item.name = name
                        item.category = array.shift      
                        item.price_in_cents = 1000
                        item.description = "its yummy"
                       
                       array.each do |ingredient|
                        new_ingredient = Ingredient.create({name: ingredient})
                       item.ingredient << new ingredient 
                    end
                        item.save
                    end
                end
                
                

