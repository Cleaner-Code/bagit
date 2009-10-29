BagIt (for ruby)
================

Based on the [BagItspec v0.95](http://www.cdlib.org/inside/diglib/bagit/bagitspec.html).

Supported Features:
-------------------
* bag compiling
* manifest & tagmanifest generation
* generation of tag files package-info.txt and bagit.txt
* fetching remote files (fetch.txt)
* bag validation

Example: making a bag
---------------------
    require 'bagit'

    # make a new bag at base_path
    bag = BagIt::Bag.new base_path  

    # make a new file    
    bag.add_file("samplefile") do |io| 
      io.puts "Hello Bag!"
    end
    
    # generate the manifest and tagmanifest files
    bag.manifest!

Example: validating an existing bag
-----------------------------------

    bag = BagIt::Bag.new existing_base_path

    if bag.valid?
      puts "#{existing_base_path} is valid"
    else
      puts "#{existing_base_path} is not valid"
    end

TODO
----
* command line tools for common tasks
* better holy bag (fetch.txt) generation
* better error reporting.
* poor mans' checksum

