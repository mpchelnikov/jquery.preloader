# jquery.preloader v1.0
A small jQuery plug-in is designed for display loading animation when some process is running. The plugin has the methods and options for controlling the displaying

Plugin includes SCSS where determines basic styles of blocks, animation, etc.

**Basic usage**

To activate plugin you should just declare parent block with 'position: relative' property, ex.: `$('.block').preloader()`.
Method 'remove' stops and removes the plugin from DOM: `$('.block').preloader('remove')`.

**Advanced usage**

Options available: _text_ (caption over the animation, string), _percent_ (percentage inside of spinning lines, string), _duration_ (lifetime of animation, in ms, string)
Example:
`$('.block').preloader({
    text: 'Hi there!',
    percent: '77',
    duration: '2000'
})`

Method 'update' updates (Cap. Obv.) text and/or percent without reinitializing plugin, ex:
`$('.block').preloader('update', {
    text: 'Hi there!',
    percent: '99'
})`
Notice: if you're init plugin without text and percent options these wouldn't work.

**Under the hood**

- Why not just `$('.myBlock').append('.preloader')`? The plugin can fill all height of parent and animation always will be at the middle of the block.
- Why parent should have 'position: relative' property? Container `<div class='preloader'></div>` has absolute position. I don't change the position property of the parent specifically not to break your layout.
- Why you aren't use "color" option to set colors? I think this feature is not often needed - better set up colors at once in css.

p.s. Thanks to Petr Tichy for spin idea