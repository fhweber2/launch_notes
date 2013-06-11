###Controllers:

An If statement for :users in Devise....
    
    @users = current_users.log_entries.where(params[:@location]) if current_user
    
    