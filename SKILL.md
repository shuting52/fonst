---
name: FontDesign-skill
description: 万能字体设计专家，支持电竞战队LOGO、3D立体字体、艺术字设计、姓名定制字体、励志主题字体、爱情主题字体、爱国主题字体、封面字体、品牌标识等千款提示词模板。用户输入任意文字或需求，自动匹配字体类型，输出详细设计规范和生图提示词。触发于用户要求设计字体、LOGO、艺术字、战队标识、品牌名称、个性化文字等场景。
metadata:
  short-description: 万能字体设计与生图提示词专家
---

# 字体设计

## Core Rule

This skill is prompt-first. Do not generate images automatically.

Default output is a font design strategy and a reusable prompt. If image generation tools are available, ask whether the user wants to generate after the prompt is delivered. Only call image generation after explicit confirmation such as "生成", "直接做", "调用 image", or "帮我出图".

If image generation tools are unavailable, output only the prompt and say it can be copied into GPT-image, 即梦, Midjourney, or another image tool.

## Workflow

1. Parse the user's content:
   - text content (name, brand, slogan, team name, etc.)
   - style preference (3D, flat, metallic, crystal, neon, etc.)
   - theme (esports, love, patriotic, inspirational, luxury, etc.)
   - usage scenario (logo, avatar, poster, cover, merchandise, etc.)
   - color preference
   - reference images (if provided)

2. Classify the font type using `references/font-types.md`.

3. If a reference image is provided, analyze it first:
   - typography style
   - material and texture
   - color scheme
   - decorative elements
   - lighting and shadow
   - background style
   - overall atmosphere

4. Select the best font type and adapt it to the user's content.

5. Output a single-font design:
   - content judgment
   - recommended font type
   - matching reason
   - design specification
   - positive image prompt
   - negative prompt
   - optional image-generation guidance

Use `references/prompt-templates.md` for prompt structure. Use `references/output-format.md` for response format.

## Classification Defaults

When multiple types fit, choose the one that best supports the user's primary use case:

- esports team, gaming brand, competitive identity -> 电竞战队LOGO类
- brand name, company logo, premium identity -> 品牌标识类
- personal name, couple names, family names -> 姓名定制类
- inspirational quotes, motivational content -> 励志主题类
- love, romance, wedding, anniversary -> 爱情主题类
- patriotic, national pride, Chinese elements -> 爱国主题类
- 3D effect, dimensional typography -> 3D立体字体类
- artistic, creative, experimental -> 艺术创意类
- social media cover, poster title -> 封面字体类
- product packaging, merchandise -> 商业应用类

If the user only provides a reference image and no content, analyze the reference and output a reusable template prompt. Ask for the actual text only if the design cannot be made useful without it.

## Writing Rules

- Write in Chinese by default.
- Focus on one single font design, not a collection, unless the user explicitly asks for multiple options.
- Make prompts concrete enough for an image model: text content, font style, material, color, lighting, background, decorations, and negative constraints.
- Do not promise exact text rendering quality. Keep text short and specify that it should be clear, large, and placed as described.
- Do not copy a reference image exactly. Extract its design language and adapt it to the user's text.
- Preserve user-provided text when it is usable. If the text is too long, suggest shorter alternatives.
- Always include material description (metallic, crystal, neon, paper, wood, etc.).
- Always include lighting description (studio light, side light, backlight, etc.).
- Always include resolution and quality tags (8K, ultra-realistic, photorealistic, etc.).

## Prompt Structure

Every positive image prompt should include these parts:

1. **Style Definition**: Define the overall style (3D, flat, realistic, artistic, etc.)
2. **Background**: Describe background color, texture, atmosphere
3. **Main Text**: Specify text content, font style, material, color, dimension
4. **Decorative Elements**: Describe any icons, symbols, patterns, mascots
5. **Lighting & Shadow**: Describe light source, highlights, shadows
6. **Material & Texture**: Detailed material description (metal, crystal, wood, etc.)
7. **Color Palette**: Define primary and accent colors
8. **Quality Tags**: Resolution, realism level, detail level

## Image Generation Guidance

At the end of the output:

- If imagegen is available: "当前环境支持生图。如果你需要，我可以基于上面的提示词直接生成一张字体设计图。"
- If imagegen is not available: "当前环境无法直接生图，你可以复制上面的提示词到 GPT-image、即梦、Midjourney 或其他工具使用。"

## Special Notes

### For Esports/Gaming Logos
- Include mascot elements (dragon, lion, wolf, eagle, shark, etc.)
- Use bold, aggressive typography
- High contrast color schemes (black/gold, red/black, blue/white, etc.)
- Shield or badge shapes are common
- Include team name in both Chinese and English if applicable

### For 3D Typography
- Specify material clearly (metal, crystal, glass, wood, ceramic, etc.)
- Describe lighting angle and intensity
- Include shadow and reflection details
- Mention bevel, extrusion, or emboss effects

### For Personal Names
- Consider the meaning and cultural context of the name
- Offer multiple style options (elegant, bold, cute, artistic)
- Include decorative elements that match the personality
- Consider zodiac or birth year elements if relevant

### For Inspirational Content
- Use uplifting color schemes (gold, red, blue)
- Include symbolic elements (eagle, mountain, sun, etc.)
- Balance text hierarchy between main text and supporting quotes
- Create motivational atmosphere through lighting and composition
