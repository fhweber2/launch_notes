
  <%= simple_form_for(@poll) do |f| %>
  <%= f.input :computers %>
  <%= f.input :copiers %>
  <%= f.input :faxmachines %>
  <%= f.input :laptops %>
  <%= f.input :monitors %>
  <%= f.input :multifunctional
  <%= f.input :printers %>
  <%= f.input :scanners %>
  <%= f.association :equipment %>
  <%= f.association :categories %>
  <%= f.button :submit %>
<% end %>