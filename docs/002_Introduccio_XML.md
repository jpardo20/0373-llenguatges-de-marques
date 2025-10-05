# **XML**  
## eXtensible Markup Language  
Sessió 1 · **Introducció al llenguatge XML**

<small>Format: reveal.js + Markdown · CC BY-NC-SA</small>

---

## Què és XML?

- **Llenguatge de marques extensible** dissenyat per **emmagatzemar i transportar dades**.  
- Basat en **text** i fàcilment llegible per **persones i màquines**.  
- No defineix com es mostra la informació, sinó **què significa**.  
- És un **estàndard** del W3C (World Wide Web Consortium).

---

## Objectius del llenguatge XML

- Facilitar l’**intercanvi de dades** entre aplicacions i sistemes.  
- Representar informació de manera **estructurada** i **auto-descriptiva**.  
- Permetre la **validació** de documents segons regles formals (DTD / XSD).  
- Ser **independent** de plataformes, llenguatges i formats de programació.

---

## Exemple bàsic

```xml
<?xml version="1.0" encoding="UTF-8"?>
<llibre>
  <titol>El nom de la rosa</titol>
  <autor>Umberto Eco</autor>
  <any>1980</any>
</llibre>
```

- `<?xml ... ?>` → declaració XML.  
- `<llibre>` és l’**arrel** del document.  
- Cada element té una **etiqueta d’obertura** i una **de tancament**.

---

## Components d’un document XML

| Component | Descripció | Exemple |
|------------|-------------|---------|
| **Element** | Un bloc d’informació | `<titol>1984</titol>` |
| **Atribut** | Propietat dins d’una etiqueta | `<llibre idioma="català">` |
| **Arrel** | Element que conté tots els altres | `<llibre>...</llibre>` |
| **Comentari** | Text explicatiu | `<!-- Exemple -->` |
| **Entitat** | Caràcter especial | `&lt; &gt; &amp;` |

---

## Regles bàsiques de sintaxi

1. Totes les etiquetes s’han de **tancar correctament**.  
2. Els elements han d’estar **ben niats**.  
3. Només pot haver-hi **un element arrel**.  
4. Els noms són **sensibles a majúscules/minúscules**.  
5. Els valors d’atributs han d’anar **entre cometes**.  

---

## Exemple d’error

```xml
<llibre>
  <titol>1984</titol>
  <autor>George Orwell
</llibre>
```

❌ L’element `<autor>` no està tancat.  
✅ Correcció:

```xml
<autor>George Orwell</autor>
```

---

## Espais de noms (namespaces)

Serveixen per **evitar conflictes** entre etiquetes de diferents vocabularis.

```xml
<producte xmlns:es="http://exemple.com/esquema">
  <es:nom>Mòbil</es:nom>
  <es:preu>350</es:preu>
</producte>
```

- `xmlns:es` defineix un prefix per identificar el conjunt d’etiquetes.  
- És essencial quan es combinen documents XML de fonts diferents.

---

## Validació de documents

### 1. **Ben format**
El document compleix les regles bàsiques de sintaxi.

### 2. **Vàlid**
A més de ser ben format, segueix una estructura definida a una **DTD** o un **XML Schema (XSD)**.

---

## Exemple amb DTD

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE llibre [
  <!ELEMENT llibre (titol, autor)>
  <!ELEMENT titol (#PCDATA)>
  <!ELEMENT autor (#PCDATA)>
]>
<llibre>
  <titol>1984</titol>
  <autor>George Orwell</autor>
</llibre>
```

---

## Avantatges de l’XML

- **Interoperable** entre aplicacions i plataformes.  
- **Llegible** per humans i processable per màquines.  
- Pot ser **validat** automàticament.  
- **Extensible**: pots definir les teves pròpies etiquetes.  
- **Estandarditzat** pel W3C.

---

## Limitacions

- Més **verbós** que altres formats (JSON, YAML).  
- No és ideal per a **dades molt grans** o **transmissions freqüents**.  
- Requereix **validació i anàlisi** més complexos.  
- Pot ser **lent** de processar en aplicacions de temps real.

---

## Comparació XML vs JSON

| Característica | XML | JSON |
|----------------|-----|------|
| Verbositat | Alta | Baixa |
| Llegibilitat | Bona | Excel·lent |
| Suport per atributs | Sí | No |
| Validació formal | DTD / XSD | JSON Schema |
| Ideal per a | Documents, dades estructurades | APIs, dades simples |

---

## Àmbits d’aplicació

- **Web**: XHTML, RSS/Atom, SVG.  
- **Configuració**: fitxers `.xml` d’aplicacions.  
- **Intercanvi de dades**: entre sistemes ERP o CRM.  
- **Bases de dades**: emmagatzematge i consultes `XQuery`.  
- **Serveis web**: SOAP, WSDL.

---

## Eines recomanades

- **Editors XML**: VS Code, oXygen XML Editor, XML Copy Editor.  
- **Validadors**: `xmllint`, Xerces, o validació en línia.  
- **Processadors**: parsers DOM, SAX, StAX.  
- **Visualització**: navegadors web o transformacions XSLT.

---

## Activitat pràctica

**Crea un fitxer `persona.xml` amb aquestes dades:**  
- nom  
- edat  
- professió  
- adreça (carrer, ciutat, codi postal)  
Afegeix un atribut `idioma` a l’element principal.  

💡 *Opcional:* crea també una petita DTD que el validi.

---

## En resum

> L’XML és un llenguatge universal per descriure informació de manera estructurada i interoperable.

---

## Fi de la sessió  
**Preguntes?** 💬  
<small>Tecles ← → · `Esc` vista global · Exporta a PDF</small>
