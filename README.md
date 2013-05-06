
# Platypus and Gem Dependencies

[Platypus](http://sveinbjorn.org/platypus) is a very cool program that turns scripts (like Perl, Ruby, or Python) into standalone applications for Mac OS X.

I found very little information on how to install Ruby gem dependencies within a Platypus app, so hopefully this will help.

To install a gem dependency in Platypus, follow these steps:

1. Download the .gem from <a href="http://rubygems.org/">RubyGems.org</a>.
2. Make a gems/ folder. Put the .gem inside.
3. Using a terminal, cd to just above the gems/ folder.
4. Install the gem locally. This should create a bunch of folders within gems/. At the terminal enter:

```
	export GEM_HOME=$PWD/gems/
	gem install --local gems/(gem_name)
```

5. Create your Platypus app, add the gems/ folder to the list of files to be bundled.
6. Then at the top of your script add:

```ruby
	require 'rubygems'
	Gem.use_paths(nil, Gem.path << 'gems/')
```

This will tell Platypus to look in the gems/ folder for the libraries you need.

Hope that helps!

