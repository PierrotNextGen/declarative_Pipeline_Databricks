# Architecture
<img width="300" height="138" alt="azure_databricks_architecture" src="https://github.com/user-attachments/assets/a22a411d-e7e4-45cf-8b93-a2fdab195e14" />







    <svg viewBox="0 0 1000 460" xmlns="http://www.w3.org/2000/svg" font-family="Arial, Helvetica, sans-serif">
  <defs>
    <marker id="arrow2" markerWidth="10" markerHeight="10" refX="8" refY="3" orient="auto" markerUnits="strokeWidth">
      <path d="M0,0 L0,6 L9,3 z" fill="#6B7280"/>
    </marker>
    <marker id="arrowRed" markerWidth="10" markerHeight="10" refX="8" refY="3" orient="auto" markerUnits="strokeWidth">
      <path d="M0,0 L0,6 L9,3 z" fill="#DC2626"/>
    </marker>
  </defs>

  <rect x="0" y="0" width="1000" height="460" fill="#FFFFFF"/>
  <text x="500" y="34" text-anchor="middle" font-size="20" font-weight="bold" fill="#111827">Azure Data Engineering Pipeline</text>
  <text x="500" y="56" text-anchor="middle" font-size="13" fill="#6B7280">Spotify dataset ingestion → data lake → transformation with CDC → secured with Key Vault</text>

  <!-- Source -->
  <rect x="30" y="160" width="140" height="80" rx="10" fill="#EEF2FF" stroke="#6366F1" stroke-width="2"/>
  <text x="100" y="192" text-anchor="middle" font-size="13" font-weight="bold" fill="#3730A3">Spotify</text>
  <text x="100" y="208" text-anchor="middle" font-size="13" font-weight="bold" fill="#3730A3">Source Data</text>
  <text x="100" y="226" text-anchor="middle" font-size="10.5" fill="#4338CA">Raw dataset</text>

  <line x1="170" y1="200" x2="218" y2="200" stroke="#6B7280" stroke-width="2" marker-end="url(#arrow2)"/>

  <!-- Data Factory -->
  <rect x="220" y="160" width="150" height="80" rx="10" fill="#FEF3C7" stroke="#D97706" stroke-width="2"/>
  <text x="295" y="192" text-anchor="middle" font-size="13" font-weight="bold" fill="#92400E">Azure Data</text>
  <text x="295" y="208" text-anchor="middle" font-size="13" font-weight="bold" fill="#92400E">Factory</text>
  <text x="295" y="226" text-anchor="middle" font-size="10.5" fill="#B45309">Orchestrates ingestion</text>

  <line x1="370" y1="200" x2="418" y2="200" stroke="#6B7280" stroke-width="2" marker-end="url(#arrow2)"/>

  <!-- ADLS Gen2 -->
  <rect x="420" y="160" width="150" height="80" rx="10" fill="#DCFCE7" stroke="#16A34A" stroke-width="2"/>
  <text x="495" y="192" text-anchor="middle" font-size="13" font-weight="bold" fill="#166534">ADLS Gen2</text>
  <text x="495" y="210" text-anchor="middle" font-size="10.5" fill="#15803D">Centralized data lake</text>
  <text x="495" y="225" text-anchor="middle" font-size="10.5" fill="#15803D">raw + processed zones</text>

  <line x1="570" y1="200" x2="618" y2="200" stroke="#6B7280" stroke-width="2" marker-end="url(#arrow2)"/>

  <!-- Databricks -->
  <rect x="620" y="150" width="180" height="100" rx="10" fill="#DBEAFE" stroke="#2563EB" stroke-width="2"/>
  <text x="710" y="180" text-anchor="middle" font-size="13" font-weight="bold" fill="#1E40AF">Azure Databricks</text>
  <text x="710" y="198" text-anchor="middle" font-size="10.5" fill="#1D4ED8">PySpark clean, transform,</text>
  <text x="710" y="212" text-anchor="middle" font-size="10.5" fill="#1D4ED8">and join datasets</text>
  <text x="710" y="230" text-anchor="middle" font-size="10.5" font-weight="bold" fill="#1D4ED8">CDC — incremental updates</text>

  <line x1="800" y1="200" x2="848" y2="200" stroke="#6B7280" stroke-width="2" marker-end="url(#arrow2)"/>

  <!-- Output -->
  <rect x="850" y="165" width="120" height="70" rx="10" fill="#F3E8FF" stroke="#9333EA" stroke-width="2"/>
  <text x="910" y="195" text-anchor="middle" font-size="12" font-weight="bold" fill="#6B21A8">Analytics-</text>
  <text x="910" y="211" text-anchor="middle" font-size="12" font-weight="bold" fill="#6B21A8">Ready Data</text>

  <!-- Key Vault -->
  <rect x="330" y="320" width="220" height="90" rx="10" fill="#FEE2E2" stroke="#DC2626" stroke-width="2"/>
  <text x="440" y="350" text-anchor="middle" font-size="13" font-weight="bold" fill="#991B1B">Azure Key Vault</text>
  <text x="440" y="370" text-anchor="middle" font-size="10.5" fill="#B91C1C">Secures credentials &amp;</text>
  <text x="440" y="385" text-anchor="middle" font-size="10.5" fill="#B91C1C">connection strings</text>

  <line x1="400" y1="320" x2="310" y2="248" stroke="#DC2626" stroke-width="1.5" stroke-dasharray="4,3" marker-end="url(#arrowRed)"/>
  <line x1="490" y1="320" x2="680" y2="256" stroke="#DC2626" stroke-width="1.5" stroke-dasharray="4,3" marker-end="url(#arrowRed)"/>
  <text x="440" y="430" text-anchor="middle" font-size="10.5" fill="#9CA3AF">Secrets injected into Data Factory and Databricks — never exposed in pipeline config</text>
</svg>
