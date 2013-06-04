    rails g model User first_name:string last_name:string email:string zipcode:string
    
____

    rails g model Game game_type_id:integer building_type_id:integer
    
___

    rails g model Game_Participant user_id:integer game_id:integer

___

    rails g model Property address:string city:string state:string zipcode:string game_participant_id:integer

___

    rails g model Bank_Transaction account:string game_participant_id:integer

____

    rails g model Implementation cost:string property_id:integer improvements_id:integer bank_transaction_id:integer

_______

    rails g model Improvements cost:string name:string saving_monthly:string

_____

    rails g model Rewards budget_increase:string redeemable_after:string
    
______

    rails g model Reward_Awards reward_id:integer bank_transaction_id:integer implementation_id:integer

