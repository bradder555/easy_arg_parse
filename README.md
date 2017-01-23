# easy_arg_parse
I think a better alternative to argparse

# installation
either git pull...
then python setup.py install
or 
pip install easy_arg_parse

# usage example
```
# program_that_needs_arguments.py
from easy_arg_parse import easy_arg_parse

if __name__ == '__main__':
    eap = easy_arg_parse.EasyArgParse\
            (
                defined_args=
                {
                    'input_dir':
                        {
                            'optional': False,
                            'help_text': "Directory containing jpgs"
                        },
                    'output_dir':
                        {
                            'optional': False,
                            'help_text': "The output directory"
                        },
                    'resize_ratio':
                        {
                            'optional': False,
                            'help_text': "How much you want to shrink the jpg as a fraction of 1 i.e. 0.75"
                        },
                    'resize_quality':
                        {
                            'optional': True,
                            "help_text": "The quality level of the saved jpg as a fraction of 1 i.e. 0.9"
                        }
                },
                aliases={
                    "i": "input_dir",
                    "in": "input_dir",
                    "o": "output_dir",
                    "out": "output_dir",
                    "ratio": "resize_ration",
                    "r": "resize_ratio",
                    "q": "resize_quality"
                }
            )
    args_dict = eap.parse()
    print("args:")
    print(args_dict) # Woah! it's a dict with all of the arguments supplied!!
    # Woah types have been inferred (i.e. str, int, float, bool)
    # Woah, a reasonable help has been printed out if mandatory arguments are missing or the help switch is used!
    ```
