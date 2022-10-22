# xiaokli.github.io

# Install Ruby

`sudo apt-get install ruby-full build-essential zlib1g-dev`

```
echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```

`gem install jekyll bundler`



## create size reduced image

* install imagemagic `sudo apt install -y imagemagic`
* reduce size `convert -resize 30% input_image_file_path output_image_file_path`
