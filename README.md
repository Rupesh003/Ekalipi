# Ekalipi
It is a language Keyboard


// QWERTY Text Area
// ********************
$('#qwerty')
    .keyboard(options)
    .addCaret({
        // extra class name added to the caret
        // "ui-keyboard-caret" class is always added
        caretClass : 'blinking-cursor',
        // *** for future use ***
        // data-attribute containing the character(s) next to the caret
        charAttr   : 'data-character',
        // # character(s) next to the caret (can be negative for RTL)
        charIndex  : 1,

        // *** caret adjustments ***
        // adjust horizontal position (pixels)
        offsetX    : 0,
        // adjust vertical position (pixels); also adjust margin-top in css
        offsetY    : 0,
        // adjust caret height (pixels)
        adjustHt   : 0
    });
    
    
    /*** Caret extension definition; included in keyboard.css ***/
/* margin-top => is added to the caret height (top & bottom) */
.ui-keyboard-caret { background: #c00; width: 1px; margin-top: 3px; }

/* Additional css to make the caret blinky; NOT included in the
 keyboard.css file */
.blinking-cursor {
  -webkit-animation: 1s blink step-end infinite;
  -moz-animation:    1s blink step-end infinite;
  -ms-animation:     1s blink step-end infinite;
  -o-animation:      1s blink step-end infinite;
  animation:         1s blink step-end infinite;
}
@keyframes "blink"         { from, to { opacity: 100%; } 50% { opacity: 0; } }
@-moz-keyframes blink      { from, to { opacity: 100%; } 50% { opacity: 0; } }
@-webkit-keyframes "blink" { from, to { opacity: 100%; } 50% { opacity: 0; } }
@-ms-keyframes "blink"     { from, to { opacity: 100%; } 50% { opacity: 0; } }
@-o-keyframes "blink"      { from, to { opacity: 100%; } 50% { opacity: 0; } }


'numpad' : {
  'normal' : [
    '{clear} / * -',
    '7 8 9 +',
    '4 5 6 %',
    '1 2 3 =',
    '0 {dec} {left} {right}'
  ]
}

$('#keyboard').keyboard({
  layout: 'custom',
  customLayout : {
    'normal': [
      '` 1 2 3 4 5 6 7 8 9 0 - = {bksp}',
      '{tab} q w e r t y u i o p [ ] \\',
      'a s d f g h j k l ; \' {enter}',
      '{shift} z x c v b n m , . / {shift}',
      '{accept} {space} {cancel} {extender}'
    ],
    'shift': [
      '~ ! @ # $ % ^ & * ( ) _ + {bksp}',
      '{tab} Q W E R T Y U I O P { } |',
      'A S D F G H J K L : " {enter}',
      '{shift} Z X C V B N M < > ? {shift}',
      '{accept} {space} {cancel} {extender}'
    ]
  }
}).addExtender({
  layout     : 'numpad',
  showing    : false,
  reposition : true
});
