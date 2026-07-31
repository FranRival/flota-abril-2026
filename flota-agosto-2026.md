# Flota Video / Imagen / Sonido — Banco de Keywords y Web Tools

Nota general: mantengo los nombres de herramienta/keyword en inglés porque es donde vive el volumen de búsqueda real (igual que en tu flota de 700 tools). Muchos de estos son viables 100% client-side con `ffmpeg.wasm`, Canvas API y Web Audio API — sin backend, coherente con el hosting estático que ya usas.

---

## 🎬 VIDEO

### Procesamiento / Análisis (calculadoras, checkers, viewers)
- video bitrate calculator
- video codec identifier / checker
- video resolution checker
- video FPS calculator
- video aspect ratio calculator
- video file size estimator
- video compression ratio calculator
- video metadata viewer / extractor
- video duration calculator
- video frame extractor (frame por frame)
- video hash / checksum checker
- video corruption checker
- video streaming bitrate (ABR ladder) calculator
- video quality calculator (VMAF / PSNR / SSIM explainer)
- video GOP size calculator
- video color space checker (SDR vs HDR, Rec.709 vs Rec.2020)
- video pixel aspect ratio calculator
- video letterbox / pillarbox calculator
- video keyframe interval calculator
- video encoding time estimator
- video render time calculator
- video storage size calculator (proyecto/backup)

### Edición
- video trimmer / cutter (client-side)
- video merger / joiner
- video cropper
- video resizer (para redes: 9:16, 1:1, 16:9)
- video rotator
- video speed changer (slow motion / timelapse)
- video reverse
- video to GIF converter
- GIF to video converter
- video subtitle burner (hardsub)
- video subtitle sync checker/adjuster
- video audio extractor (mp4 → mp3)
- video mute / audio remover
- video looper
- video watermark adder
- video watermark remover (ojo: zona gris legal, evaluar)
- video color grading tool (LUT preview)
- video brightness/contrast/saturation adjuster
- video frame rate converter (24→30, 30→60)
- video split screen maker
- video compressor (client-side, sin subir a servidor)
- video format converter (mp4 ↔ webm ↔ mov ↔ avi)
- video chapter marker generator
- video timestamp/burned-in timecode generator
- video freeze frame tool
- video thumbnail generator / picker
- video intro/outro trimmer
- video social media crop presets (TikTok/Reels/Shorts)

### Limpieza / Mejora
- video upscaler (AI, 480p→1080p, etc.)
- video denoiser
- video deblur tool
- video stabilizer
- video deinterlacer
- video HDR ↔ SDR converter
- video auto color/exposure enhancer
- old video restoration tool
- video artifact/banding remover
- video low-light enhancer

---

## 🖼️ IMÁGENES

### Procesamiento / Análisis
- image dimension calculator
- image DPI calculator (print sizing)
- image file size calculator
- image aspect ratio calculator
- image color palette extractor
- image dominant color finder
- image histogram viewer
- image EXIF viewer / remover
- image hash generator (perceptual hash / MD5 / dHash)
- image format identifier
- image bit depth checker
- image compression ratio calculator
- image color contrast checker (WCAG accessibility)
- image color blindness simulator
- image similarity / duplicate checker
- image resolution vs print size calculator
- image megapixel calculator

### Edición
- image cropper
- image resizer (bulk resize)
- image rotator / flipper
- image background remover
- image background changer / replacer
- image watermark adder / remover
- image collage maker
- image merger / combiner (side by side)
- image splitter (grid cutter, Instagram carousel splitter)
- image border / frame adder
- image meme generator (texto sobre imagen)
- image filter applier (sepia, B/N, vintage)
- image format converter (webp ↔ avif ↔ png ↔ jpg ↔ heic)
- image color picker (eyedropper desde archivo)
- image pixelate tool
- image blur tool (privacidad, rostros/placas)
- image sharpen tool
- image rounded corner generator
- image circle crop tool
- image duotone generator
- image gradient overlay tool
- image favicon generator
- image sprite sheet generator
- image placeholder generator (blurhash, LQIP)
- image mockup generator (device frames)
- image contact sheet / grid generator
- image bulk renamer + resizer

### Limpieza / Mejora
- image upscaler (AI super resolution)
- image denoiser
- image deblur tool
- image compressor (lossy/lossless, bulk)
- image auto-enhance (brillo/contraste/color automático)
- old photo restoration / colorizer (IA)
- image scratch remover
- image red-eye remover
- image skin smoother / retoucher
- image object remover (inpainting)
- image low-light enhancer
- image background noise/grain reducer

---

## 🔊 SONIDO / AUDIO

### Procesamiento / Análisis
- audio bitrate calculator
- audio sample rate converter info
- audio file size calculator
- audio duration calculator
- audio waveform generator / viewer
- audio spectrogram generator
- audio metadata (ID3) viewer / editor
- audio format identifier
- audio loudness meter (LUFS calculator, estándar streaming)
- audio BPM detector
- audio key detector
- audio pitch detector
- audio silence detector
- audio clipping detector
- audio fingerprint / hash checker

### Edición
- audio trimmer / cutter
- audio merger / joiner
- audio format converter (mp3 ↔ wav ↔ ogg ↔ flac ↔ aac)
- audio speed changer (sin cambiar pitch)
- audio pitch shifter (sin cambiar velocidad)
- audio volume normalizer
- audio fade in/out tool
- audio reverse tool
- audio looper (para música/ambientes)
- audio channel splitter (stereo → mono, L/R split)
- audio simple multi-track mixer
- audio silence remover/auto-trim
- ringtone maker
- audio to text transcription tool
- text to speech tool
- audio joiner con crossfade

### Limpieza / Mejora
- audio noise reducer (ruido de fondo)
- audio denoiser (hiss/hum removal)
- audio voice enhancer (claridad de voz)
- audio equalizer (presets: voz, música, podcast)
- audio compressor (dinámica)
- audio de-esser
- audio hum/hiss remover (60Hz/50Hz)
- audio echo/reverb remover
- vocal remover / isolator (karaoke maker)
- old recording restoration tool

---

## 🧠 Ideas transversales (cross-media)
- comparadores "X vs Y" de formatos (webp vs avif, mp4 vs webm, flac vs mp3, etc.) — buen contenido educativo + tool embebido
- "how much does X minute video/audio weigh at Y bitrate" — calculadoras tipo long-tail
- calculadoras de tiempo de subida/descarga según velocidad de internet (video/audio/imagen)
- checkers de compatibilidad de formato por plataforma (¿Instagram acepta este códec?)
- generadores de specs para plataformas (YouTube, TikTok, Spotify, Podcasts) — tamaños, bitrates, duraciones recomendadas

## Nota de viabilidad técnica
- Video/imagen: `ffmpeg.wasm` + Canvas API cubren la gran mayoría sin backend, pero ojo con el peso de la wasm y límites de memoria en móvil — quizá conviene poner un límite de tamaño de archivo o avisar "recomendado para clips cortos".
- Audio: Web Audio API cubre casi todo (waveform, EQ, pitch, mezcla básica); para BPM/key detection hay librerías JS ligeras (ej. Essentia.js) que también corren en el navegador.
- Todo esto respeta tu restricción de sitios estáticos con procesamiento 100% client-side.
