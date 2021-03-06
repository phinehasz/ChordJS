和弦JS图
=======  
和弦图, 基础例子在 test.html  
```
<chord name="D-maj7" positions="x-x-10-10-9-9" fingers="--2311" size="4" ></chord>
<chord name="A-sus" positions="x02230" fingers="--123-" size="4" ></chord>
```
name: 代表和弦名, 如果有附加部分则使用 '-', 会在旁边展示  
如果是高把位10以上的和弦, 需要用 '-' 分隔符  
该ChordJs作为基础组件, 理论上支持所有和弦

ChordJS 
=======

Draw guitar chord diagrams on HTML5 canvas

Chords.js is a small javascript library to generate images of guitar chords in HTML. It can display chord boxes, starting frets, barred chords, fingerings and open and muted strings.  

into images like:

![Image of a D Chord](http://chords.einaregilsson.com/D.png?p=xx0232&f=---132&s=3 "D Chord")
![Image of a A Chord](http://chords.einaregilsson.com/A.png?p=x02220&f=--123-&s=3 "A Chord")
![Image of a A Chord](http://chords.einaregilsson.com/A_5.png?p=577655&f=134211&s=3 "A bar Chord")

There is a small example at test.html.  

To use chords.js you can simply convert the url format of the parent library into markup as follows:

* &lt;chord name="D" positions="xx0232" fingers="---132" size="3" &gt;&lt;/chord&gt;
* &lt;chord name="A" positions="x02220" fingers="--123-" size="3" &gt;&lt;/chord&gt;
* &lt;chord name="A-5" positions="577655" fingers="134211" size="3" &gt;&lt;/chord&gt;

Then include script similar to the following on your page:

    <script src="http://ajax.googleapis.com/ajax/libs/jquery/1.8/jquery.min.js"></script>
    <script src="chords.js"></script>
    <script type="text/javascript">//<![CDATA[
    $(document).ready(function(){
        ChordJS.replace();
    });
    //]]>
    </script>

## Documentation

### Syntax

#### &lt;chord name="..." positions="..." fingers="..." size="..." layout="..." strings="..."  &gt;&lt;/chord&gt; elements

#### ChordJS.generate(name, positions, fingering, size, layout, strings)
Returns a chord diagram as a canvas element, which can easily be added to the DOM.

### Options

 - name
    Name of the Chord. E.g.: `C#`
 - positions
    Fret positions for each string. Muted string = `x`; Open string = 0. E.g.: `x02220`
 - fingers  
    Fingers to use for each string. No finger = `-`. E.g.: `--123-` (you can use different characters if you like)
 - size
    The size of the chord diagram to generate. E.g.: `3` for medium size or `5` for a pretty big size.
 - layout (optional, default: `'1'`)
    The layout for the chord diagram.   
    `'1'` would draw the finger names onto the strings and show the string names below the diagram.  
    `'2'` would draw the finger names below the chord diagrams and not dispaly the string names.  
 - strings (optional)  
    Names of the strings. E.g. `EADGBe` for standard tuning.  

#### ChordJS.replace(baseElement)

Replace `<chord>` elements with rendered chord diagrams.

 - baseElement (optional)
    The element in which to replace the <chord> elements.

## License
The source is licensed under the GPL. 
