# ffmpeg commands

ffmpeg commands can appear tricky. Here's one I made that's long and seems scary to look at:

```
ffmpeg -y -hide_banner \
-i changed0.8/changed_keyframe01.png \
-i changed0.8/changed_keyframe02.png \
-i changed0.8/changed_keyframe03.png \
-i changed0.8/changed_keyframe04.png \
-i changed0.8/changed_keyframe05.png \
-i changed0.8/changed_keyframe06.png \
-i changed0.8/changed_keyframe07.png \
-i changed0.8/changed_keyframe08.png \
-i changed0.8/changed_keyframe09.png \
-i changed0.8/changed_keyframe010.png \
-i changed0.8/changed_keyframe11.png \
-i changed0.8/changed_keyframe12.png \
-i changed0.8/changed_keyframe13.png \
-i changed0.8/changed_keyframe14.png \
-i changed0.8/changed_keyframe15.png \
 -filter_complex "\
[0]scale=w=1080:h=ih*1080/iw,pad='1080:1920:(ow-iw)/2:(oh-ih)/2',scale=w=4000:h=ih*4000/iw,zoompan=z='zoom+0.001':x='iw/2-iw/zoom/2':y='ih/2-ih/zoom/2':d=100:s=1080x1920,format=yuv420p[p0]; \
[1]scale=w=1080:h=ih*1080/iw,pad='1080:1920:(ow-iw)/2:(oh-ih)/2',scale=w=4000:h=ih*4000/iw,zoompan=z='zoom+0.001':x='iw/2-iw/zoom/2':y='ih/2-ih/zoom/2':d=100:s=1080x1920,format=yuv420p[p1]; \
[2]scale=w=1080:h=ih*1080/iw,pad='1080:1920:(ow-iw)/2:(oh-ih)/2',scale=w=4000:h=ih*4000/iw,zoompan=z='zoom+0.001':x='iw/2-iw/zoom/2':y='ih/2-ih/zoom/2':d=100:s=1080x1920,format=yuv420p[p2]; \
[3]scale=w=1080:h=ih*1080/iw,pad='1080:1920:(ow-iw)/2:(oh-ih)/2',scale=w=4000:h=ih*4000/iw,zoompan=z='zoom+0.001':x='iw/2-iw/zoom/2':y='ih/2-ih/zoom/2':d=100:s=1080x1920,format=yuv420p[p3]; \
[4]scale=w=1080:h=ih*1080/iw,pad='1080:1920:(ow-iw)/2:(oh-ih)/2',scale=w=4000:h=ih*4000/iw,zoompan=z='zoom+0.001':x='iw/2-iw/zoom/2':y='ih/2-ih/zoom/2':d=100:s=1080x1920,format=yuv420p[p4]; \
[5]scale=w=1080:h=ih*1080/iw,pad='1080:1920:(ow-iw)/2:(oh-ih)/2',scale=w=4000:h=ih*4000/iw,zoompan=z='zoom+0.001':x='iw/2-iw/zoom/2':y='ih/2-ih/zoom/2':d=100:s=1080x1920,format=yuv420p[p5]; \
[6]scale=w=1080:h=ih*1080/iw,pad='1080:1920:(ow-iw)/2:(oh-ih)/2',scale=w=4000:h=ih*4000/iw,zoompan=z='zoom+0.001':x='iw/2-iw/zoom/2':y='ih/2-ih/zoom/2':d=100:s=1080x1920,format=yuv420p[p6]; \
[7]scale=w=1080:h=ih*1080/iw,pad='1080:1920:(ow-iw)/2:(oh-ih)/2',scale=w=4000:h=ih*4000/iw,zoompan=z='zoom+0.001':x='iw/2-iw/zoom/2':y='ih/2-ih/zoom/2':d=100:s=1080x1920,format=yuv420p[p7]; \
[8]scale=w=1080:h=ih*1080/iw,pad='1080:1920:(ow-iw)/2:(oh-ih)/2',scale=w=4000:h=ih*4000/iw,zoompan=z='zoom+0.001':x='iw/2-iw/zoom/2':y='ih/2-ih/zoom/2':d=100:s=1080x1920,format=yuv420p[p8]; \
[9]scale=w=1080:h=ih*1080/iw,pad='1080:1920:(ow-iw)/2:(oh-ih)/2',scale=w=4000:h=ih*4000/iw,zoompan=z='zoom+0.001':x='iw/2-iw/zoom/2':y='ih/2-ih/zoom/2':d=100:s=1080x1920,format=yuv420p[p9]; \
[10]scale=w=1080:h=ih*1080/iw,pad='1080:1920:(ow-iw)/2:(oh-ih)/2',scale=w=4000:h=ih*4000/iw,zoompan=z='zoom+0.001':x='iw/2-iw/zoom/2':y='ih/2-ih/zoom/2':d=100:s=1080x1920,format=yuv420p[p10]; \
[11]scale=w=1080:h=ih*1080/iw,pad='1080:1920:(ow-iw)/2:(oh-ih)/2',scale=w=4000:h=ih*4000/iw,zoompan=z='zoom+0.001':x='iw/2-iw/zoom/2':y='ih/2-ih/zoom/2':d=100:s=1080x1920,format=yuv420p[p11]; \
[12]scale=w=1080:h=ih*1080/iw,pad='1080:1920:(ow-iw)/2:(oh-ih)/2',scale=w=4000:h=ih*4000/iw,zoompan=z='zoom+0.001':x='iw/2-iw/zoom/2':y='ih/2-ih/zoom/2':d=100:s=1080x1920,format=yuv420p[p12]; \
[13]scale=w=1080:h=ih*1080/iw,pad='1080:1920:(ow-iw)/2:(oh-ih)/2',scale=w=4000:h=ih*4000/iw,zoompan=z='zoom+0.001':x='iw/2-iw/zoom/2':y='ih/2-ih/zoom/2':d=100:s=1080x1920,format=yuv420p[p13]; \
[14]scale=w=1080:h=ih*1080/iw,pad='1080:1920:(ow-iw)/2:(oh-ih)/2',scale=w=4000:h=ih*4000/iw,zoompan=z='zoom+0.001':x='iw/2-iw/zoom/2':y='ih/2-ih/zoom/2':d=100:s=1080x1920,format=yuv420p[p14]; \
[p0][p1]xfade=transition=fadewhite:duration=0.5:offset=1.5[f0]; \
[f0][p2]xfade=transition=diagbl:duration=0.5:offset=3.0[f1]; \
[f1][p3]xfade=transition=squeezev:duration=0.5:offset=4.5[f2]; \
[f2][p4]xfade=transition=wiperight:duration=0.5:offset=6.0[f3]; \
[f3][p5]xfade=transition=slideright:duration=0.5:offset=7.5[f4]; \
[f4][p6]xfade=transition=pixelize:duration=0.5:offset=9.0[f5]; \
[f5][p7]xfade=transition=wipebr:duration=0.5:offset=10.5[f6]; \
[f6][p8]xfade=transition=hlslice:duration=0.5:offset=12.0[f7]; \
[f7][p9]xfade=transition=wiperight:duration=0.5:offset=13.5[f8]; \
[f8][p10]xfade=transition=wipeup:duration=0.5:offset=15.0[f9]; \
[f9][p11]xfade=transition=diagbl:duration=0.5:offset=16.5[f10]; \
[f10][p12]xfade=transition=smoothup:duration=0.5:offset=18.0[f11]; \
[f11][p13]xfade=transition=wipebr:duration=0.5:offset=19.5[f12]; \
[f12][p14]xfade=transition=diagbl:duration=0.5:offset=21.0[f13]; \
" \
-map "[f13]" -t 22.5  -pix_fmt yuv420p  -vcodec libx264  output.mp4
```

It looks crazy but really, it's pretty repetitive. Actually, I didn't even write that whole thing myself. I wrote a script to do it for me. ffmpeg commands can be long but they're fairly modular and you can just choose whatever you want. 

# ffmpeg for cowards (like me!)

A guide to becoming a little less scared. I looked for countless alternatives to ffmpeg (for example using a real video scripting with Python on DaVinci Resolve: a free video editing application) before finally coming back to it. And genuinely all because I was a little scared and overwhelmed by some of the ffmpeg 'magic' commands out there. 

Also naming ```complex filtergraphs``` "complex filtergraphs" was a terrible idea. It puts learners off (like me!) because they think “oh no it’s probably too complex”. I fiddled with MoviePy for a month before deciding it’s way too slow.

It's a small jump from simple filtergraphs. Basically, the difference is simple filtergraphs take one input and has one output. Complex filtergraphs can have multiple inputs and multiple outputs (or just one!).

I’ll start by making you run some simple ffmpeg commands so you get your hands dirty. Then I move onto slightly longer commands by combining them. Easy.

Here are some simple examples for common complex_filter commands to help you get started:

vstack = Vertically stack multiple inputs
```
ffmpeg -i input0.mp4 -i input1.mp4 -i input2.mp4 -filter_complex "vstack=inputs=3" output.mp4
```

hstack = Horizontally stack multiple inputs, need to be same height, pretty useful for comparisons side-by-side
```
ffmpeg -i input0.mp4 -i input1.mp4 -i input2.mp4 -filter_complex "hstack=inputs=3" output.mp4
```

scale = Resize the input, very useful
```
ffmpeg -i input0.mp4 -filter_complex "scale=w=1080" output.mp4
```

Combining scale and vstack
For example, when input0.mp4 is the problem and the input needs to be 1080 by 1920 (standard for phone screens)
```
ffmpeg -i input0.mp4 -i input1.mp4 -i input2.mp4 -filter_complex "[0]scale=w=1080;[v0][1][2]vstack=inputs=3" output.mp4
```

pad = Adding padding to the sides
Combining pad and vstack
```
ffmpeg -i input0.mp4 -i input1.mp4 -i input2.mp4 -filter_complex "[0]pad='1080:1920:(ow-iw)/2:(oh-ih)/2'[v0];[v0][1][2]vstack=inputs=3" output.mp4
```

crop = crop the frame to your preferred dimensions
Basically, just choose a rectangle from inside your input
You have to specify the width, height, and optionally the x,y co-ordinates
If you don't specify x,y, it picks (in_w-out_w)/2 and (in_h-out_h)/2 (Basically the center of the frame)
Crop with vstack
```
ffmpeg -i input0.mp4 -i input1.mp4 -i input2.mp4 -filter_complex "[0]crop=[v0];[v0][1][2]vstack=inputs=3" output.mp4
```

# How to parse ffmpeg. 
This is how I read ffmpeg commands and have found it to be useful to me. 

Sometimes you come across a stackoverflow question or a reddit thread where someone has written an absolute magic spell. In those cases, and just in general when writing my own commands, this is a list of things I like to do to decode the magic.

There's commands out there that are really messy so the first thing I do is make them legible. That means new line for each section. What do I mean by that?

I mean, I rewrite the crazy one liner command as follows:

```
ffmpeg

-input options -inputs
-input options -inputs
-input options -inputs    #All I do is count how many inputs there are
-input options -inputs    #and ignore the input-specific options
-input options -inputs

-filter_complex

"
[variable]filter,filter,filter,filter[variable];
[variable]filter,filter,filter,filter[variable];    #filters in the same chain use commas
[variable]filter,filter,filter,filter[variable];    #To break a filter chain, use semicolons
[variable]filter,filter,filter,filter[variable];    #Each output for a filter must be consumed
[variable]filter,filter,filter,filter[variable];    #Once and only once
[variable]filter,filter,filter,filter[FINAL]        #I always break each filter chain out into different lines
"

-output file options (generally some map[FINAL] format etc etc ) #I ignore this too lol
FILENAME.WHATEVERTYPE   #gotta name it something cool
```

By doing this, I find that the command is easier for me to read.
I look at the filters first, the input-specific options (if any) second, and the output-options (if any new ones) last.
If there's anything new in the filters that I don't recognize (or its using more inputs than I do lol), I'll dip into the documentation
Same with input options, and output options.
