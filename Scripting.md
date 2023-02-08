## Shebang Line: #!/usr/bin/env python
-This piece is important to include in your Python scripts to make them readable as a Python object

## Shebang in script: #!/bin/bash
-your scripting file is going to end in .sh
-In your bash file, you are going to write
  -python [absolute path to your python file]

## Make your file readable: chmod +x hello.py
-When you chmod +x it is important that you are in the directory that your script is in or else it won't find the file

## Look at your PATH variable via echo $0. If this shows zsh instead of something like /usr/bin/zsh, you need to update your path variable
-update path variables by export $PATH = Path
-export PATH=$PATH:/home/richard.chuang/projects/repositories/customer-migrations/custom_migrations/ats/Jobvite/helpers/jobvite_mapping_helper.py

## We want to have user inputs in the scripts which are read into the Python script
-in your script, you use 'echo input something' (print statement) then 'read some_variable' (input statement). Then, next to your script, add your variables like so:
-python /home/richard.chuang/projects/repositories/customer-migrations/custom_migrations/ats/Jobvite/helpers/jobvite_mapping_helper.py \
"$customer_name" "$path_to_jobvite_source_directory" "$target_path" "$path_to_org_data"
-Now, within your Python script, you need to import sys. This will allow us to use the argv method which calls on the inputs we created earlier. Remember, that the indexing for these variables starts at 1 instead of 0, with 0 being the title script.
-customer_name = sys.argv[1]
path_to_jobvite_source_directory = sys.argv[2]
target_path = sys.argv[3]
path_to_org_data = sys.argv[4]
