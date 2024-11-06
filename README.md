# Typografie für Web und UI

Enno Hyttrek, November 2024

---

### Typografie – Allgemeine Begriffserklärung

Typografie ist die Gestaltung und Anordnung von Texten, um Kommunikation visuell ansprechend und funktional zu machen. Sie umfasst das Auswählen von Schriftarten, das Festlegen von Schriftgrößen, Zeilenabständen, Laufweiten und weiteren Details, die das Lesen und Verstehen erleichtern oder unterstützen. Traditionell stammt die Typografie aus dem Druckbereich, hat sich aber im digitalen Zeitalter stark weiterentwickelt und an digitale und responsive Medien angepasst.

**Schlüsselkonzepte der Typografie:**

- **Schriftfamilie (Font Family)**: Eine Sammlung von Schriftarten in einem bestimmten Stil, wie z. B. Serifenschriften (mit kleinen Linien an den Enden der Buchstaben) und serifenlose Schriften (ohne solche Linien), die unterschiedlich wahrgenommen werden. Serifenlose Schriften sind oft besser auf Bildschirmen lesbar.
- **Schriftgröße und -gewicht**: Die visuelle Hierarchie kann über verschiedene Größen und Stärken betont werden, was wichtig für die Struktur und Orientierung auf einer Seite ist.
- **Zeilenhöhe (Line-Height)** und **Laufweite (Letter-Spacing)**: Diese bestimmen die Abstände zwischen Zeilen und Buchstaben und haben Einfluss auf die Lesbarkeit. Eine angenehme Zeilenhöhe liegt in der Regel bei 1.5 (1.5-mal der Schriftgröße).

---

### Typografie für das Web – Gestalterische Überlegungen

Im Web hat Typografie eine besondere Bedeutung, da sie maßgeblich zur User Experience beiträgt. Anders als im Printbereich muss Webtypografie flexibel und anpassbar sein, um auf verschiedenen Geräten gut lesbar zu sein.

**Gestalterische Aspekte für die Webtypografie:**

- **Visuelle Hierarchie und Lesbarkeit**: Klare Hierarchien helfen Nutzern, Inhalte schneller zu erfassen. Headlines (`<h1>`, `<h2>`, etc.), Zwischenüberschriften und Fließtext sollten optisch differenziert sein. 

  Beispiel:
  
  ```css
  h1 {
      font-size: 2em;
      font-weight: bold;
      line-height: 1.2;
  }

  p {
      font-size: 1em;
      line-height: 1.6;
  }
  ```

- **Responsivität**: Texte müssen auf mobilen und Desktop-Geräten gleichermaßen gut lesbar sein. Man kann mit `rem` und `em` arbeiten, um eine flexible Typografie zu ermöglichen, die sich je nach Bildschirmgröße anpasst. Responsive Breakpoints für Schriftgrößen helfen, eine angenehme Lesbarkeit auf allen Geräten zu gewährleisten.

  Beispiel mit Media Queries:

  ```css
  body {
      font-size: 1em;
  }

  @media (min-width: 768px) {
      body {
          font-size: 1.2em;
      }
  }
  ```

- **Konsistenz**: Einheitliche Schriftarten und Stilrichtungen sorgen für einen professionellen Auftritt und geben dem Nutzer eine klare Orientierung.

- **Lesefluss und Textaufteilung**: Lange Texte sollten in Absätze und Unterkapitel gegliedert werden. Schmale Spalten erhöhen auf mobilen Geräten die Lesbarkeit, während Desktop-Bildschirme breitere Textspalten zulassen.

**Weitere gestalterische Entscheidungen:**

- **Schriftfarbe und Kontrast**: Hoher Kontrast zwischen Text und Hintergrundfarbe verbessert die Lesbarkeit und ist ein Grundsatz für barrierefreies Webdesign. `color` und `background-color` in CSS unterstützen diesen Effekt.
- **Textausrichtung und -richtung**: Der Lesefluss von links nach rechts oder oben nach unten ist für westliche Kulturen natürlich; aber für andere Sprach- und Lesegewohnheiten muss dies berücksichtigt werden.

---

### Typografie für das Web – Technische Überlegungen

Neben der Gestaltung spielt die Technik eine zentrale Rolle. CSS bietet zahlreiche Möglichkeiten, Texte zu stylen, und mit Webfonts können Designer auf eine große Vielfalt an Schriftarten zugreifen, ohne auf die Geräte-Standardschriften beschränkt zu sein.

**CSS und Schriften im Detail:**

- **Schriftfamilien und Fallbacks**: Wenn eine Schriftart nicht geladen werden kann, sorgen Fallback-Schriftarten für eine bessere Nutzererfahrung. Ein Fallback kann so definiert werden:

  ```css
  body {
      font-family: 'Arial', 'Helvetica', sans-serif;
  }
  ```

- **Webfonts und @font-face**: Webfonts ermöglichen die Einbindung von Schriftarten, die nicht auf dem Gerät des Nutzers installiert sind. `@font-face` definiert benutzerdefinierte Schriften.

  ```css
  @font-face {
      font-family: 'MyCustomFont';
      src: url('/fonts/MyCustomFont.woff2') format('woff2');
  }

  body {
      font-family: 'MyCustomFont', sans-serif;
  }
  ```

- **Barrierefreiheit**: Texte müssen für alle Nutzer zugänglich sein. W3C-Standards (z. B. WCAG) fordern etwa hohe Kontraste, flexible Schriftgrößen und semantische HTML-Elemente, die von Screenreadern erkannt werden können.

- **Lesbarkeit und Browserkompatibilität**: CSS-Eigenschaften wie `font-kerning` oder `font-variant` werden möglicherweise nicht von allen Browsern unterstützt. Tools wie `@supports` helfen dabei, CSS abhängig von der Unterstützung eines Browsers zu verwenden.

  ```css
  @supports (font-kerning: normal) {
      p {
          font-kerning: normal;
      }
  }
  ```

---

### Typografie im UI-Design für Mobile und Desktop

Für Apps gelten zusätzliche Regeln: Lesbarkeit und Benutzerfreundlichkeit müssen in einem begrenzten Raum gewährleistet sein, und der Text sollte sich an verschiedenen Bildschirmgrößen und Interaktionen orientieren.

**Wichtige Punkte im UI-Design:**

- **Skalierbarkeit und adaptive Typografie**: Die Typografie sollte sich an die Größe und Auflösung des Bildschirms anpassen. `vw` und `vh` können in CSS für responsive Größen genutzt werden.

  ```css
  h1 {
      font-size: 5vw;
  }
  ```

- **Berührungsfreundliche Gestaltung**: Größere Abstände und Berührungsflächen sind wichtig für mobile Geräte, um ungewollte Berührungen zu vermeiden.

- **Typografie und Hierarchie in Apps**: Mobile Apps profitieren von klarer visueller Hierarchie, die durch Größenunterschiede und Gewicht der Schriften erreicht wird.

  Ein Beispiel:

  ```css
  .app-title {
      font-size: 24px;
      font-weight: 700;
  }

  .app-subtitle {
      font-size: 18px;
      font-weight: 500;
  }
  ```

- **Gestaltung für kurze Lesezeiten**: In Apps wird oft nur kurz und in kleinen Häppchen gelesen. Text sollte daher möglichst klar und prägnant formuliert sein, da Nutzer Apps oft in Bewegung verwenden.

Durch diese tiefere Betrachtung von Typografie im digitalen Kontext wird deutlich, wie die Kombination von gestalterischen und technischen Elementen eine einheitliche und ansprechende Nutzererfahrung schaffen kann.