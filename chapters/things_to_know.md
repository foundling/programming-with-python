Indentation matters.

def print_list(l):

    for item in l:
        print item 

It is dynamic:
    
person = { 'name': 'alex' } 

# wait, I change my mind
person['name'] = 'Al';

# wait, I change my mind
person = 'robot'

# wait, I change my mind
person = 1 

# don't do that sort of stuff, btw

person = { 
    'name': 'alex', 
    'status': 'wiser'
}


and strongly typed:

    # I'm an error
    "a" + 1

but intercompatible:

    [ i*2 for i in [1,2,3,4] ]
    # [ 2,4,6,8 ]

    [ letter for letter in "elephant" ]
    # [ "e","l","e","p","h","a","n","t" ]


    expanded_list = 1 * [4]
    # expanded_list is [4,4,4,4]

    keys = list({'one':'two', 'three': 'four'})
    # keys is ['one','three']

It allows you to be succinct.

    markdown_headers = [ 

        line
        for line in lines
        if line.strip().startswith('#') 

    ] 


