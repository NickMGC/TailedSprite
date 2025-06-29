# Tailed Sprite
A specialized `TailedSprite` class for the [HaxeFlixel](https://haxeflixel.com/) game engine, designed specifically for rendering sustain notes in rhythm games.
<br/>
This class extends `FlxSprite` to provide tiling capabilities, making it easy to create dynamically-sized sustain notes. This class also supports animated sprites, flipping and rotation.

The frame gap fix was made by [RapperGF](https://github.com/rappergf)

## Usage

Here is a basic example of how to use `TailedSprite` in your project:

```haxe
var sustain:TailedSprite = new TailedSprite();
sustain.loadGraphic("assets/sustain.png", true, 50, 50);
sustain.animation.add("body", [0], 25);
sustain.animation.add("tail", [1], 25);
sustain.animation.play("body");

// Specify the animation to use for the tail
sustain.setTail("tail");

add(sustain);

/* 
 * In your update loop, you can dynamically change the height
 * This is useful for when a player is holding a sustain note
 */
override public function update(elapsed:Float):Void
{
    super.update(elapsed);
    sustain.update(elapsed);
    sustain.height = ...; // Your height logic here
}
```
