# Welcome to MkDocs

For full documentation visit [mkdocs.org](https://www.mkdocs.org).

## Commands

* `mkdocs new [dir-name]` - Create a new project.
* `mkdocs serve` - Start the live-reloading docs server.
* `mkdocs build` - Build the documentation site.
* `mkdocs -h` - Print help message and exit.

## Project layout

    mkdocs.yml    # The configuration file.
    docs/
        index.md  # The documentation homepage.
        ...       # Other markdown pages, images and other files.

## Salamn
```

    from PIL import Image # Open the image image = Image.open('image.jpg') 
    # Calculate the scaling factor scaling_factor = 160 / 1280  
    # Calculate the new size of the image 
    new_size = (int(image.width * scaling_factor), int(image.height * scaling_factor)) 
    # Resize the image resized_image = image.resize(new_size, resample=Image.BICUBIC) 
    # Save the resized image resized_image.save('resized_image.jpg')
