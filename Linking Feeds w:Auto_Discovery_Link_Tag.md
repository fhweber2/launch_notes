Linking to Feeds with the auto_discovery_link_tag

2 parameters 

Linking to Feeds with the auto_discovery_link_tag

The auto_discovery_link_tag helper builds HTML that most browsers and newsreaders can use to detect the presences of RSS or ATOM feeds. It takes the type of the link (:rss or :atom), a hash of options that are passed through to url_for, and a hash of options for the tag:

    <%= auto_discovery_link_tag(title: "RSS Feed") %>


There are three tag options available for the auto_discovery_link_tag:

    rel:     #specifies the rel value in the link. The default value is “alternate”.
    type:    #specifies an explicit MIME type. Rails will generate automatically.
    title:   #specifies the title of the link. 
             #The default value is the upshifted :type value, for example, “ATOM” or “RSS”.
