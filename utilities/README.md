utilities
==========

### console

- stops errors with no console in older browsers

### underscore cache templates from ajax

- render underscore templates from an ajax request
- allows you to store a js template within your rails views folder structure

###### I would put _template.html in my corresponding view folder for this controller then:

    # routes
    get '/controller_name/template' => "controller#template", :as => :controller_template

    # controller
    def template
      # need to make sure rails doesn't parse our tags or return anything compiled
      render :text => File.read(Rails.root.join('app/views/controller_name/_template.html'))
    end