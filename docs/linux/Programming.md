# Linux Shell Programming

## Tools

<http://trevorjim.com/awk-unix-and-functional-programming/>


## Awk

* for loop: <https://gist.github.com/cdosborn/563c0e62b050fa95ce22>
	
	```
	BEGIN {
	    for (i in ARGV) {
	        if (ARGV[i] == "--sep") {
	            sep = ARGV[i + 1];
	            "echo \'" sep "\'" | getline sep
	        }
	        ARGV[i] = "";
	    }
	}
	{
	    for (i = 1; i <= NF; i++) {
	        if (field_length[i] < length($i)) {
	            field_length[i] = length($i);
	        }
	    }
	    lines[NR] = $0;
	}
	END {
	    "tput cols" | getline cols
	    if (!sep) {
	        longest_line += reduce(field_length, 0, "add");
	        gaps = length(field_length) - 1
	        excess = cols - longest_line
	        sep = sprintf("%-" trunc(excess / gaps) "s", " ")
	    }
	 
	    for (l in lines) {
	        len = split(lines[l], arr, / +/);
	        for (i = 1; i <= len; i++) {
	            if (i == len) {
	                printf "%s", arr[i]
	            } else {
	                pad = field_length[i];
	                printf ("%-" pad "s" sep), arr[i], sep
	            }
	        }
	        print "";
	    }
	}
	```