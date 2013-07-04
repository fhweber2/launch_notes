###APIs

JSON / XML Formats

####XML

    <article>
        <title> Title </title>
        
        <body> Da Body </body>
        
    </article>
    
Take a look at the MailChimp API


RESTful


Nokogiri -- web scrapping (frowned upon in the industry)

<http://nokogiri.org/>


Live Code! " A Weather Crawler"

    bundle gem weather
    
________

An Energy Star Gem? 

###Gem:

    Files -> lib 
    weather.rb

    weather .gemspec
____

    .rspec

    gem 'vcr'

    gem 'webmock'

"Yak Shaving" - cut through the shit before you can get to the root of what you're trying to do!


    gem.add_development_dependency 

Rspec

    describe 'WeatherCrawler' do
        it 'gets a weather report' do
            report = Weather::Report.new('02210')
            report.retrive
            expect(report.temperature).to_not be_nil
            expect(report.condtional).to_not be_nil
        end
    end

Weather Module
    
    require 'open-uri'
    
    module Weather
        class Report
            def initialize(postal_code)
            @postal_code = postal_code
        end
        
        def retrieve
            url = "some url"
            doc = Nokogiri                          # use CGI to escape the url
                                            
                                                            
    # use the inspector on the desired page using CSS ex. (doc.css ('#hour00)
        end
    end

Goto a Weather Site (enter the zip '02210') 

Using CSS Selectors to pull data from the site   (doc.css) then plug/play

Use binding.pry to parse the data 

    doc.css('#curCond').first.content 
    
    doc.css('#rapidtemp span.b').first.content 
    
    
###Nokogiri:

<http://nokogiri.org/tutorials/parsing_an_html_xml_document.html>


