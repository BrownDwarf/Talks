Dissertation talk
---

###This is my dissertation talk.

I am using [reveal.js](https://github.com/hakimel/reveal.js/), which is awesome but a little wonky in how it interacts with IPython Notebook.

### Changing global configurations
On my machine to get this to work you need to directly customize the `slides_reveal.tpl` file, which is a jinja template file.  On my system this file is located in my IPython directory, here:  
`$HOME/anaconda/pkgs/ipython-3.1.0-py27_0/lib/python2.7/site-packages/IPython/nbconvert/templates/html/`

There *is* a way to configure the reveal customizations locally, rather than edit the global configuration template above.  But configuring locally didn't seem to work for me.  So I just settled on my hack above.  It is definitely a hack because what happens when I go to upgrade my IPython installation later?  It'll be *lights-out* for my global template.  So much bad about this strategy, but it seems to work, so I am running with it.

### Compiling the slideshow from IPython Notebook
To get the presentation to actually run, you need to run this command:  
`ipython nbconvert PhD_talk_01_exploratory.ipynb --to slides --post serve`

The command to add a local configuration file (which, again, did not work for me) is:  
`ipython nbconvert PhD_talk_01_exploratory.ipynb --to slides --post serve -config setup_template.py`

Damian Avila has some more info about this on his blog.