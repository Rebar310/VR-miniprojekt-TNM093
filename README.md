
<img width="1898" height="979" alt="image" src="https://github.com/user-attachments/assets/277af957-184d-4428-b940-30393dc8a429" />

<img width="1912" height="988" alt="image" src="https://github.com/user-attachments/assets/81e9767a-5a85-4cb7-84cb-c81db7a124d4" />

### **Task 9**

För **motion parallax** behöver du i praktiken bara låta **kameran röra sig när du rör huvudet**. Det får du i VR-labbet genom att byta till en **head-tracked** vy. Texturerna du redan lagt (checker på golv/vägg) ger bra kontraster så parallaxen blir tydlig.

## Gör så här (minsta ändring i din fil)

1. **Byt vy till head-tracked + mono** (stereo AV—uppgiften vill jämföra med stereon avstängd):

```xml
<!-- Stäng av untracked-läget -->
<!-- <Inline url="urn:candy:x3d/view-untracked-mono.x3d"/> -->
<!-- <Inline url="urn:candy:x3d/view-untracked-stereo.x3d"/> -->

<!-- Sätt PÅ head-tracked monoscopic -->
<Inline url="urn:candy:x3d/view-head-tracked-mono.x3d"/>
<!-- Om du vill testa även head-tracked stereo senare:
<Inline url="urn:candy:x3d/view-head-tracked-stereo.x3d"/>
-->

```

1. **Behåll dina texturer** (golv/vägg med PixelTexture + TextureTransform). De ger högfrekvent struktur → starkare parallax-ledtrådar.
2. **NavigationInfo kan stå kvar** – i tracked-läget ignoreras mus-orbit och kameran följer trackern: `<NavigationInfo type='"EXAMINE" "ANY"' headlight="false"/>`

3. **Se till att tracker-servern är igång i labbet** (krav i instruktionen). Din `IMPORT ... HDEV` används redan i dina ROUTEs för kontrollskripten; kamerans tracking sköts av den inladdade tracked-view X3D-filen.
