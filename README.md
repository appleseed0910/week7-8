# Week7-8 Checkpoint

DGM6410 Game Design Tech Lab

This repository contains:


-  Inquiry
-  Research notes
-  Futher Research expectations

## Research
### 1. More details about the style/formatting in Twine
After I finished the demo for the last checkpoint, I can obviously feel some places that I need to learn more skills to adjust for a better visual experience. So, I keep searching more techiques that allow me to do more editing on the style and formati aspect.

- Get rid of extra whitespace

When I tried to put multiple nested macros together, the awkward white space is annoying. The way to get rid of it is put a pair of curly brackets outside the content that I want to eliminate extra whitespace.
```
{Welcome to the world inside the mirror.

A strange bottle on the table.(click: "bottle")[ The liquid inside is purple looks like a dream of galaxy.]}
```
The white space in this example would be ignored defaultly.

- Trvial of Fonts

It's easy and quick to change font using CSS stylesheet. Whereas there's acutally a font macro which allows me to change the font in a certain place and overwrite the CSS style. More flexiable.
```
(font: "courier new")[contents]  // The contents after would be shown in a courier font.
```
Some regular fonts that could be used without extra importing here: **Palatino**, **Times New Roman**, **Arial, Lucida**, **Comic Sans**, **Tahoma**, **Trebuchet**, **Imapct**, **Papyrus**. (always reminds me the character in the game Undertale.)

- Sepcial Effects

Besides basic fonts, there're some special text effects macros that allow us to present the story more dynamic.
```
(text-style:"mark")[bottle]
```
The 'bottle' would be marked in yellow as a highlight here.

Here're many other styles that we could use contain: "italic", "bold", "under-line", "strike"

Some dynamic and fun ones: **blink**, **rumble**, **fade-in-out**, **shudder**, **blur/blurrier**, **smear**, **mirror**, **upside-down**.

- One time text effect

If the dynamic effect keeps making the text rumbling or blinking would be disturbing, we could use the trasition macro to control it.
```
(transition: "pulse")[text]
```
As written, the text here would only pulse for once. Three effects that could be connected to the transition macro are **pulse**, **dissolve**, **shudder**.

- Import Google Fonts

If the default fonts are not enough we could import fonts from Google online fonts library and add to the story stylesheet.
```
@import url('https://fonts.googleapis.com/css?family=Mina');
tw-passage{font-family: 'Mina', sans-serif;}
```
The story text would be shown in the online font 'Mina' here.

### 2. Several trivial but important macros
During the research, I found there're couple macros that I forgot to mention in previous checkpoint. But they're important espcially for games. So, I add them here.

 - Random and Either
 
 Either macro is for randomly presenting a result from an array.
 ```
 (either: "mirror", "window")  // randomly show the mirror or window
 ```
If we could use it combined with variable, it could become more flexiable and useful.
```
(set:$variableName to (either:"mirror","window"))
(print: $variableName)
```
Through this code, we could use the random object that the story generated before anywhere in the game.

For generating a random number, the random macro could be used. 
```
(random:2,12)  // Generate a random number between 2 and 12
```
This kind of random macro is suitable for a dice roll game with a pair of dice.

With this, it could also be easy for us to generate a random character datamap with a sequence of properties at the beginning of the game.

 - Append and Prepend
 
 These two macros are handy to use with some hidden hints. Especially, when they are with the click or mouse-over, it could even be eaiser than click-reveal to manage the story structure.
 ```
 (click-append: "Ughhhh")[What's that?]
 (mouseover-prepend: "The text before the content.")[Body text.]
 ```
 We could also use them combined with special tags.

