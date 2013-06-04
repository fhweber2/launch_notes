
#Reading and Writing Files

###Create, append, read, etc. from files in Ruby

**Stick to relative paths in your files

    hello = 'hello from a file'
    File.open('hello.txt', 'w' ) do |f|
    f.puts hello
    end
    
    cat hello.txt
    hello from a file
    
    File.read ('hello.txt')
    "hello from a file\n"
                                                    #extra spaces (2) use chomp to trim
    File.read('hello.txt').chomp
    
    
Standard files = .csv and .yml (or YAML)

        YAML (yml)
            -first_name: "Dan"
            last_name: "Pickett"
            -first_name: "Jason"
            last_name: "Zopf"
            
        CSV (csv)
            "Dan", "Picket"
            "Jason", "Zopf"
            