# Bash Scripting

## 1) Notes

Utility: getopts

```bash
    getopts optstring name [args...]
```

Key Components:

- optstring: A string containing the recognized option characters.
  If an option character is followed by a colon (:), it signifies that the option expects an argument.
  For example, ab:c means -a and -c are options without arguments, while -b requires an argument.
- name: The name of a shell variable that getopts sets to the option character found during each iteration.
- args... (optional): The list of parameters to be parsed. If omitted, getopts parses the positional parameters ($@).

## 2) Special Parameters

### 2.1) Parameter: "$@"

Info: List of script input parameters
Example

```bash
    echo "Arguments received:"
    for arg in "$@"; do
        echo "- \"$arg\""
    done
```

### 2.2) Parameter: "$?"

Info: Exit status of the last executed command

### 2.3) Parameter: "$#"

Info: Number of script input parameters

## 2) Scripting

### 2.1) Case Statement

```bash
    case expression in
    pattern1)
        # Commands to execute if expression matches pattern1
        ;;
    pattern2)
        # Commands to execute if expression matches pattern2
        ;;
    a) # This is the specific pattern you asked about
        # Commands to execute if expression matches 'a'
        ;;
    *) # Default case (optional), matches anything not matched by previous patterns
        # Commands to execute for the default case
        ;;
    esac
```

### 2.2) Function Parameter flags

```bash
    my_advanced_function() {
        local opt_a=""
        local opt_b=""
        local positional_arg=""

        while getopts "ab:" opt; do
            case $opt in
            a)
                opt_a="true"
                ;;
            b)
                opt_b="$OPTARG"
                ;;
            \?)
                echo "Invalid option: -$OPTARG" >&2
                return 1
                ;;
            esac
        done
        shift $((OPTIND - 1)) # Shift positional arguments after options

        if [ -n "$opt_a" ]; then
            echo "Option -a was provided."
        fi

        if [ -n "$opt_b" ]; then
            echo "Option -b with value: $opt_b"
        fi

        if [ -n "$1" ]; then
            positional_arg="$1"
            echo "Positional argument: $positional_arg"
        fi
    }
```

Example calls

```bash
    my_advanced_function -a -b "value" "some_file.txt"
    my_advanced_function -b "another_value"
    my_advanced_function
```
