Persist a user for Devise:

before_filter :authenticate_user!


def create
    @widget = Widget.new(params[:widge])
    @widget.user = current_user
    
    if @widget.save
        redirect_to widgets_path
    
    else
        render 'new'
    
    end