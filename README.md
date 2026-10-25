# 네른스트 전위 계산기

명시한 반응지수와 온도로 평형 전극·전지 전위 계산

- Plan ID: E094
- App: https://nanalab.kr/eng-nernst-potential/
- Repository: https://github.com/NaNaCompany/eng-nernst-potential
- Formula: `E = E° − RT lnQ/(nF)`
- Output: 반응 전위 E

## Model

T,Q>0, n은 양의 정수. E°와 Q는 동일 방향 반응·기준을 사용하고 Q는 활동도 기반 무차원 값이다. 전류 부하·과전압·내부저항·임의 농도지수 산정은 제외한다.

Inputs are normalized to SI. Only one scalar is returned. Model conditions, finite numbers, physical boundaries, overflow and underflow are checked. External solver APIs and property databases are not used.

## Verification

Run `node --test tests/*.test.mjs` with Node.js 22 or later. Independent 70-digit Decimal example result: `-0.0591593496847823`. Source and license notices are in [SOURCES.md](SOURCES.md) and [LICENSE](LICENSE).

## Hosting

GitHub Pages uses `main` and `/`, with the NaNaCompany domain inherited. Google GTM, GA4, AdSense, Cloudflare analytics and the gray More Apps link are included. All code, descriptions and graphics are original.

## Static languages

Korean (existing root), English (`en/`), Spanish (`es/`), Simplified Chinese (`zh/`), Japanese (`ja/`) and German (`de/`). Each page has its own canonical URL, reciprocal hreflang, localized metadata, interface, validation messages and preview image. The language links work without JavaScript. Calculation code is shared and no runtime translation API is used.

Edit `localization/*.json` for text, `src/template.html` for the shared page, and run `python scripts/build-locales.py`. Run `python scripts/build-locales.py --check` and `npm test` before publishing. Decimal commas are accepted in Spanish and German; thousands separators are not supported.
