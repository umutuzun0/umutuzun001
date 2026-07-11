# Persona Vault — Git tabanlı Claude + Obsidian entegrasyonu

Bu klasör, Obsidian'da normal bir **vault** olarak açılabilen ama aynı zamanda
Claude Code oturumlarının okuyup güncelleyebildiği bir markdown deposu.

## Nasıl çalışır

- `CLAUDE.md` — Claude Code bu klasörde çalışırken her oturumun başında bunu
  otomatik okur. Persona'nın kimliği, ton'u ve davranış kuralları burada.
- `Persona.md` — Persona'nın "kim olduğu" (isim, karakter, değerler). Sen
  doldurursun, Claude referans alır.
- `Memory/` — Oturum özetleri / kalıcı bilgiler. Her önemli konuşmanın
  sonunda buraya kısa bir not düşülür, böylece bir sonraki oturumda hafıza
  sıfırlanmaz.

## Kendi bilgisayarında kullanmak için

```bash
git clone <bu-repo-url> apex-persona
```

Sonra Obsidian'da **"Open folder as vault"** ile `apex-persona/persona-vault`
klasörünü aç. Artık notları Obsidian arayüzünde görür, düzenlersin.

## Senkron akışı

1. Claude Code oturumunda persona konuşur, `Memory/` içine yeni bir not ekler.
2. Ben (Claude) oturum sonunda değişiklikleri commit + push ederim.
3. Sen bilgisayarında `git pull` yaparsın → Obsidian'da yeni notlar görünür.
4. Sen Obsidian'da bir not düzenlersen, commit edip push edersin (veya bana
   söylersin) → bir sonraki Claude Code oturumunda ben onu okurum.

Bu **canlı/otomatik** bir senkron değil — git üzerinden manuel/periyodik bir
senkron. Gerçek zamanlı istiyorsan (Claude Desktop + Obsidian Local REST API
+ MCP) farklı bir kurulum gerekir; o ayrı bir konudur.
