# 🎨 NEXUS AI — Color Palette & Design Tokens

## Primary Colors (NEVER CHANGE)

| Name | Hex | RGB | Use Case |
|---|---|---|---|
| Primary Orange | `#FF6B35` | rgb(255,107,53) | CTA buttons, hero highlights, Visor glow |
| Deep Navy | `#0A1929` | rgb(10,25,41) | Main background |
| Accent Gold | `#FFD700` | rgb(255,215,0) | Halo ring, premium tier, star ratings |
| Pure White | `#FFFFFF` | rgb(255,255,255) | Body text, card backgrounds |
| Dark Gray | `#333333` | rgb(51,51,51) | Secondary text |
| Deep Red | `#CC0000` | rgb(204,0,0) | Jellyfish glow, energy accents |
| Card BG | `#0D2137` | rgb(13,33,55) | Service/Pricing card backgrounds |

## Glow Effects
| Effect | CSS Value |
|---|---|
| Orange glow | `box-shadow: 0 0 40px rgba(255,107,53,0.35)` |
| Gold glow | `box-shadow: 0 0 30px rgba(255,215,0,0.3)` |
| Red glow | `box-shadow: 0 0 25px rgba(204,0,0,0.25)` |
| Text glow | `text-shadow: 0 0 20px rgba(255,107,53,0.5)` |

## Gradients
| Name | CSS Value |
|---|---|
| CTA Button | `linear-gradient(135deg, #FF6B35, #FFD700)` |
| Dark Section | `linear-gradient(135deg, #0f2027, #203a43, #2c5364)` |
| Timeline Line | `linear-gradient(90deg, #CC0000, #FF6B35, #FFD700, #FFFDE7)` |
| Card Hover | `linear-gradient(135deg, #0D2137, #1a3a5c)` |

## Typography
| Role | Font | Weight | Size |
|---|---|---|---|
| Display/Logo | Orbitron | 700-900 | 32-64px |
| Headings | Orbitron | 700 | 24-48px |
| Body | Inter | 300-400 | 14-18px |
| UI/Buttons | Space Grotesk | 600-700 | 14-16px |
| Badge/Label | Space Grotesk | 700 | 11-12px |

## CSS Variables (paste in :root)
```css
:root {
  --primary-orange:  #FF6B35;
  --deep-navy:       #0A1929;
  --accent-gold:     #FFD700;
  --pure-white:      #FFFFFF;
  --dark-gray:       #333333;
  --deep-red:        #CC0000;
  --card-bg:         #0D2137;
  --border-glow:     rgba(255, 107, 53, 0.3);
  --gold-glow:       rgba(255, 215, 0, 0.3);
  
  --font-display:    'Orbitron', sans-serif;
  --font-body:       'Inter', sans-serif;
  --font-ui:         'Space Grotesk', sans-serif;
  
  --transition-fast:  0.2s ease;
  --transition-mid:   0.4s ease;
  --transition-slow:  0.8s ease;
  
  --border-radius-sm: 8px;
  --border-radius-md: 16px;
  --border-radius-lg: 24px;
  --border-radius-pill: 50px;
}
```
