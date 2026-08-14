<img width="300" height="120" alt="aws_insurance_architecture" src="https://github.com/user-attachments/assets/6bbd6943-8d2b-4ece-9256-4880b132aa58" />
<svg viewBox="0 0 1000 400" xmlns="http://www.w3.org/2000/svg" font-family="Arial, Helvetica, sans-serif">
  <defs>
    <marker id="arrow3" markerWidth="10" markerHeight="10" refX="8" refY="3" orient="auto" markerUnits="strokeWidth">
      <path d="M0,0 L0,6 L9,3 z" fill="#6B7280"/>
    </marker>
  </defs>

  <rect x="0" y="0" width="1000" height="400" fill="#FFFFFF"/>
  <text x="500" y="34" text-anchor="middle" font-size="20" font-weight="bold" fill="#111827">Insurance Claims Data Pipeline (AWS)</text>
  <text x="500" y="56" text-anchor="middle" font-size="13" fill="#6B7280">Raw claims data → data lake → automated ETL → data warehouse → SQL analytics</text>

  <!-- Raw sources -->
  <rect x="30" y="150" width="150" height="90" rx="10" fill="#EEF2FF" stroke="#6366F1" stroke-width="2"/>
  <text x="105" y="185" text-anchor="middle" font-size="13" font-weight="bold" fill="#3730A3">Raw Claims</text>
  <text x="105" y="203" text-anchor="middle" font-size="13" font-weight="bold" fill="#3730A3">Data Sources</text>

  <line x1="180" y1="195" x2="228" y2="195" stroke="#6B7280" stroke-width="2" marker-end="url(#arrow3)"/>

  <!-- S3 -->
  <rect x="230" y="150" width="150" height="90" rx="10" fill="#DCFCE7" stroke="#16A34A" stroke-width="2"/>
  <text x="305" y="182" text-anchor="middle" font-size="13" font-weight="bold" fill="#166534">Amazon S3</text>
  <text x="305" y="200" text-anchor="middle" font-size="10.5" fill="#15803D">Scalable data lake</text>
  <text x="305" y="215" text-anchor="middle" font-size="10.5" fill="#15803D">raw + processed layers</text>

  <line x1="380" y1="195" x2="428" y2="195" stroke="#6B7280" stroke-width="2" marker-end="url(#arrow3)"/>

  <!-- Glue -->
  <rect x="430" y="150" width="150" height="90" rx="10" fill="#FEF3C7" stroke="#D97706" stroke-width="2"/>
  <text x="505" y="185" text-anchor="middle" font-size="13" font-weight="bold" fill="#92400E">AWS Glue</text>
  <text x="505" y="203" text-anchor="middle" font-size="10.5" fill="#B45309">Automates ETL</text>
  <text x="505" y="218" text-anchor="middle" font-size="10.5" fill="#B45309">ingestion &amp; transform</text>

  <line x1="580" y1="195" x2="628" y2="195" stroke="#6B7280" stroke-width="2" marker-end="url(#arrow3)"/>

  <!-- Redshift -->
  <rect x="630" y="150" width="160" height="90" rx="10" fill="#DBEAFE" stroke="#2563EB" stroke-width="2"/>
  <text x="710" y="182" text-anchor="middle" font-size="13" font-weight="bold" fill="#1E40AF">Amazon Redshift</text>
  <text x="710" y="200" text-anchor="middle" font-size="10.5" fill="#1D4ED8">Curated data</text>
  <text x="710" y="215" text-anchor="middle" font-size="10.5" fill="#1D4ED8">warehouse</text>

  <line x1="790" y1="195" x2="838" y2="195" stroke="#6B7280" stroke-width="2" marker-end="url(#arrow3)"/>

  <!-- Analytics -->
  <rect x="840" y="150" width="130" height="90" rx="10" fill="#F3E8FF" stroke="#9333EA" stroke-width="2"/>
  <text x="905" y="185" text-anchor="middle" font-size="12" font-weight="bold" fill="#6B21A8">SQL Analytics</text>
  <text x="905" y="203" text-anchor="middle" font-size="12" font-weight="bold" fill="#6B21A8">&amp; Reporting</text>

  <text x="20" y="380" font-size="10.5" fill="#9CA3AF">Glue automates the movement of data from S3 into Redshift for reporting</text>
</svg>
