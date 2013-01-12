.. _extensions:

Extensions
============


Pluggable
----------

Use PyBB as a pluggable comment system. By registering a model, you can have every created instance to have its Topic, and display Posts as comments.  


Register model
***************

.. code-block:: python

    from pybb_extensions.pluggable.models import register as pybb_register
    
    class MyModel(models.Model):
        ...
        
        """Required. To which forum should we save the Topic?"""
        def forum_id(self):
	        return 123
		
        """Not required. Defaults to string representation."""
        def forum_topic_title(self):
            return self.title
		
        """Not required. Defaults to string representation."""
        def forum_topic_body(self):
            return '<a href="%s">You should see this! "%s"</a>' % (self.get_absolute_url(), (self.title or 'hello world'))
		
        """Not required. Defaults to now."""
        def forum_topic_added(self):
            return self.date_added
	        
    pybb_register(MyModel)


Display comments
*****************

.. code-block:: django

	{% load pybb_pluggable_tags %} {# or add_to_builtins('pybb_extensions.pluggable.templatetags.pybb_pluggable_tags') #}
	
	{% if obj.has_plug %}		
	    {% pluggable_topic obj user %}	    
	    {% if user.is_authenticated %}
	        {% pluggable_topic_form obj user %}
	    {% endif %}	    
	{% endif %}

	
Search
-------

#TODO
