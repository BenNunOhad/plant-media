# Plant Media Assets

Media files for the Plant Memory app (צמחי ישראל).

## Structure

```
plant-media/
├── thumbnails/     # 150x150 px (for grid view)
│   ├── 3.png
│   ├── 7.png
│   └── ...
├── images/         # 800x800 px (for full screen view)
│   ├── 3.png
│   ├── 7.png
│   └── ...
└── audio/          # 30-60 sec audio descriptions
    ├── 3.wav
    ├── 7.wav
    └── ...
```

## Level 1 Plants (Free Tier)

These plants are downloaded on first app launch:

| ID | Hebrew Name | English Name |
|----|-------------|--------------|
| 3 | חצב מצוי | Common Squill |
| 7 | אורן ירושלים | Aleppo Pine |
| 9 | זית אירופי | Olive Tree |
| 13 | שקד מצוי | Almond Tree |
| 25 | צבר מצוי | Prickly Pear |
| 42 | חרוב מצוי | Carob Tree |
| 71 | לוטם שעיר | Rock-rose |
| 89 | תאנה | Fig Tree |
| 90 | רימון מצוי | Pomegranate |
| 118 | אורן הצנובר | Stone Pine |
| 136 | לוטם מרווני | Sage-leaved Rock-rose |

## Replacing Placeholder Images

To replace placeholder images with real ones:

1. **Thumbnails**: 150x150 px, PNG or WebP format
2. **Images**: 800x800 px, PNG or WebP format  
3. **Audio**: 30-60 seconds, WAV or M4A/AAC format

### Converting to WebP (smaller size)

```bash
# Install webp tools
brew install webp

# Convert thumbnails
for f in thumbnails/*.png; do 
  cwebp -q 80 "$f" -o "${f%.png}.webp"
done

# Convert images
for f in images/*.png; do 
  cwebp -q 85 "$f" -o "${f%.png}.webp"
done
```

### Converting audio to M4A

```bash
# Install ffmpeg
brew install ffmpeg

# Convert audio
for f in audio/*.wav; do 
  ffmpeg -i "$f" -c:a aac -b:a 64k "${f%.wav}.m4a"
done
```

## URL Format

Files are served from GitHub raw content:

```
https://raw.githubusercontent.com/BenNunOhad/plant-media/main/thumbnails/3.png
https://raw.githubusercontent.com/BenNunOhad/plant-media/main/images/3.png
https://raw.githubusercontent.com/BenNunOhad/plant-media/main/audio/3.wav
```
