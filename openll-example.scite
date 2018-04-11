// Create and initialize font face

LLhandle fontface = 0;

llCreateFontFace(1, & fontface);

const char * fontFaceContents = 0x0; // load from file OpenSans.fnt

llLoadFontFaceData(fontface, LL_FONTFACE_FORMAT_DISTANCE_FIELD_FONT_FILE, fontFileContents);


// Create and initialize text

LLhandle text = 0;

llCreateText(1, &text);

llLoadTextContents(text, LL_TEXT_INTERNAL_FORMAT_UC32, LL_TEXT_ENCODING_ANSII, 0, "Hello Word");


// Derive glyph sequence

LLhandle glyphsequence = 0;

llCreateGlyphSequence(1, &glyphsequence);

llAssignGlyphSequenceText(glyphsequence, text);
llAssignGlyphSequenceFontFace(glyphsequence, fontface);

// llSetGlyphSequenceAttrib(glyphsequence, LL_TYPESET_WORD_WRAP, LL_TRUE);
llSetGlyphSequenceAttrib(glyphsequence, LL_TYPESET_ALIGNMENT, LL_TYPESET_ALIGNMENT_LEFT_ALIGNED);
llSetGlyphSequenceAttrib(glyphsequence, LL_TYPESET_LINE_ANCHOR, LL_TYPESET_LINE_ANCHOR_BASELINE);
llSetGlyphSequenceAttrib(glyphsequence, LL_TYPESET_LINE_ANCHOR, LL_TYPESET_LINE_ANCHOR_BASELINE);
llSetGlyphSequenceAttrib(glyphsequence, LL_TYPESET_FONT_SIZE, 12.0);
llSetGlyphSequenceAttrib(glyphsequence, LL_TYPESET_FONT_SIZE_UNIT, LL_SIZE_UNIT_PT);
llSetGlyphSequenceAttrib(glyphsequence, LL_TYPESET_POSITION, { 100, 200 });
llSetGlyphSequenceAttrib(glyphsequence, LL_TYPESET_POSITION_UNIT, LL_SIZE_UNIT_PX);


// Surface

LLhandle surface llCreateSurface(LL_OPENGL_DEFAULT_FRAMEBUFFER_SURFACE, GL_BACK_LEFT);

// llSetSurfaceAttrib(surface, LL_SURFACE_DEVICE_PIXEL_RATIO, 2.0);
// llSetSurfaceAttrib(surface, LL_SURFACE_REFERENCE_PIXEL_PER_INCH, 72.0);
llSetSurfaceAttrib(surface, LL_SURFACE_PIXEL_PER_INCH, 120.0);
llSetSurfaceAttrib(surface, LL_SURFACE_VIEWPORT, { 0, 0, 1920, 1080 });


// Render

LLhandle renderer = llCreateRenderer(LL_RENDERER_OPENGL);

llSetRendererAttrib(renderer, LL_RENDERER_SUPERSAMPLING, LL_TRUE);
llSetRendererAttrib(renderer, LL_RENDERER_ENABLE_FONT_COLORS, LL_FALSE);

llRenderGlyphSequence(renderer, surface, glyphsequence);


// Cleanup

destroyRenderer(renderer);
destroySurface(surface);
destroyGlyphSequence(glyphsequence);
destroyFontFace(fontface);
destroyText(text);
