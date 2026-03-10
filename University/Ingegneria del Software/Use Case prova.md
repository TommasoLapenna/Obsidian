<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1400 1150" width="1400" height="1150" font-family="Segoe UI, Arial, sans-serif">

  <!-- Background -->
  <rect width="1400" height="1150" fill="#F8F9FA" rx="12"/>

  <!-- Title -->
  <text x="700" y="40" text-anchor="middle" font-size="22" font-weight="bold" fill="#1A1A2E">Sistema PC Builder – Diagramma Use Case UML</text>
  <line x1="100" y1="52" x2="1300" y2="52" stroke="#CCCCCC" stroke-width="1.5"/>

  <!-- ═══════════════════════════════════════════════════ -->
  <!-- SYSTEM BOUNDARY -->
  <!-- ═══════════════════════════════════════════════════ -->
  <rect x="270" y="65" width="870" height="1055" rx="10" fill="white" stroke="#3A86FF" stroke-width="2" stroke-dasharray="8,4"/>
  <text x="705" y="88" text-anchor="middle" font-size="13" font-weight="bold" fill="#3A86FF">«system» PC Builder Online</text>

  <!-- ═══════════════════════════════════════════════════ -->
  <!-- ZONE COLORATE PER MACRO-AREA -->
  <!-- ═══════════════════════════════════════════════════ -->

  <!-- Account -->
  <rect x="285" y="95" width="840" height="105" rx="8" fill="#EFF6FF" stroke="#93C5FD" stroke-width="1"/>
  <text x="300" y="112" font-size="11" font-weight="bold" fill="#1D4ED8">GESTIONE ACCOUNT</text>

  <!-- Configurazione -->
  <rect x="285" y="210" width="840" height="245" rx="8" fill="#F0FDF4" stroke="#86EFAC" stroke-width="1"/>
  <text x="300" y="228" font-size="11" font-weight="bold" fill="#15803D">CONFIGURAZIONE PC</text>

  <!-- Ordine e Pagamento -->
  <rect x="285" y="465" width="840" height="165" rx="8" fill="#FFF7ED" stroke="#FDB974" stroke-width="1"/>
  <text x="300" y="483" font-size="11" font-weight="bold" fill="#C2410C">ORDINE E PAGAMENTO</text>

  <!-- Operatore -->
  <rect x="285" y="640" width="840" height="145" rx="8" fill="#FDF4FF" stroke="#D8B4FE" stroke-width="1"/>
  <text x="300" y="658" font-size="11" font-weight="bold" fill="#7E22CE">GESTIONE OPERATORE</text>

  <!-- Consegna -->
  <rect x="285" y="795" width="840" height="95" rx="8" fill="#FFF1F2" stroke="#FDA4AF" stroke-width="1"/>
  <text x="300" y="813" font-size="11" font-weight="bold" fill="#BE123C">CONSEGNA</text>

  <!-- Admin -->
  <rect x="285" y="900" width="840" height="200" rx="8" fill="#F0F9FF" stroke="#7DD3FC" stroke-width="1"/>
  <text x="300" y="918" font-size="11" font-weight="bold" fill="#0369A1">AMMINISTRAZIONE</text>

  <!-- ═══════════════════════════════════════════════════ -->
  <!-- USE CASES – ACCOUNT -->
  <!-- ═══════════════════════════════════════════════════ -->
  <!-- UC01 -->
  <ellipse cx="430" cy="140" rx="72" ry="24" fill="white" stroke="#3A86FF" stroke-width="1.5"/>
  <text x="430" y="136" text-anchor="middle" font-size="10" fill="#1e293b" font-weight="bold">UC01</text>
  <text x="430" y="149" text-anchor="middle" font-size="9.5" fill="#334155">Registrazione</text>

  <!-- UC02 -->
  <ellipse cx="620" cy="140" rx="72" ry="24" fill="white" stroke="#3A86FF" stroke-width="1.5"/>
  <text x="620" y="136" text-anchor="middle" font-size="10" fill="#1e293b" font-weight="bold">UC02</text>
  <text x="620" y="149" text-anchor="middle" font-size="9.5" fill="#334155">Login / Logout</text>

  <!-- UC03 -->
  <ellipse cx="820" cy="140" rx="72" ry="24" fill="white" stroke="#3A86FF" stroke-width="1.5"/>
  <text x="820" y="136" text-anchor="middle" font-size="10" fill="#1e293b" font-weight="bold">UC03</text>
  <text x="820" y="149" text-anchor="middle" font-size="9.5" fill="#334155">Gestione Profilo</text>

  <!-- ═══════════════════════════════════════════════════ -->
  <!-- USE CASES – CONFIGURAZIONE -->
  <!-- ═══════════════════════════════════════════════════ -->
  <!-- UC04 -->
  <ellipse cx="400" cy="255" rx="80" ry="24" fill="white" stroke="#16a34a" stroke-width="1.5"/>
  <text x="400" y="251" text-anchor="middle" font-size="10" fill="#1e293b" font-weight="bold">UC04</text>
  <text x="400" y="264" text-anchor="middle" font-size="9.5" fill="#334155">Avvia Configurazione</text>

  <!-- UC05 -->
  <ellipse cx="620" cy="255" rx="80" ry="24" fill="white" stroke="#16a34a" stroke-width="1.5"/>
  <text x="620" y="251" text-anchor="middle" font-size="10" fill="#1e293b" font-weight="bold">UC05</text>
  <text x="620" y="264" text-anchor="middle" font-size="9.5" fill="#334155">Seleziona Componente</text>

  <!-- UC06 – extends UC05 -->
  <ellipse cx="840" cy="255" rx="80" ry="24" fill="#dcfce7" stroke="#16a34a" stroke-width="1.5" stroke-dasharray="5,3"/>
  <text x="840" y="251" text-anchor="middle" font-size="10" fill="#1e293b" font-weight="bold">UC06</text>
  <text x="840" y="264" text-anchor="middle" font-size="9.5" fill="#334155">Verifica Compatibilità</text>

  <!-- UC07 -->
  <ellipse cx="400" cy="330" rx="80" ry="24" fill="white" stroke="#16a34a" stroke-width="1.5"/>
  <text x="400" y="326" text-anchor="middle" font-size="10" fill="#1e293b" font-weight="bold">UC07</text>
  <text x="400" y="339" text-anchor="middle" font-size="9.5" fill="#334155">Verifica Disponibilità</text>

  <!-- UC08 -->
  <ellipse cx="620" cy="330" rx="80" ry="24" fill="white" stroke="#16a34a" stroke-width="1.5"/>
  <text x="620" y="326" text-anchor="middle" font-size="10" fill="#1e293b" font-weight="bold">UC08</text>
  <text x="620" y="339" text-anchor="middle" font-size="9.5" fill="#334155">Rimuovi/Sostituisci</text>

  <!-- UC09 -->
  <ellipse cx="840" cy="330" rx="80" ry="24" fill="white" stroke="#16a34a" stroke-width="1.5"/>
  <text x="840" y="326" text-anchor="middle" font-size="10" fill="#1e293b" font-weight="bold">UC09</text>
  <text x="840" y="339" text-anchor="middle" font-size="9.5" fill="#334155">Riepilogo Config.</text>

  <!-- UC10 -->
  <ellipse cx="430" cy="410" rx="80" ry="24" fill="white" stroke="#16a34a" stroke-width="1.5"/>
  <text x="430" y="406" text-anchor="middle" font-size="10" fill="#1e293b" font-weight="bold">UC10</text>
  <text x="430" y="419" text-anchor="middle" font-size="9.5" fill="#334155">Salva Configurazione</text>

  <!-- UC11 -->
  <ellipse cx="700" cy="410" rx="80" ry="24" fill="white" stroke="#16a34a" stroke-width="1.5"/>
  <text x="700" y="406" text-anchor="middle" font-size="10" fill="#1e293b" font-weight="bold">UC11</text>
  <text x="700" y="419" text-anchor="middle" font-size="9.5" fill="#334155">Carica Config. Salvata</text>

  <!-- ═══════════════════════════════════════════════════ -->
  <!-- USE CASES – ORDINE -->
  <!-- ═══════════════════════════════════════════════════ -->
  <!-- UC12 -->
  <ellipse cx="430" cy="510" rx="85" ry="24" fill="white" stroke="#ea580c" stroke-width="1.5"/>
  <text x="430" y="506" text-anchor="middle" font-size="10" fill="#1e293b" font-weight="bold">UC12</text>
  <text x="430" y="519" text-anchor="middle" font-size="9.5" fill="#334155">Invia Richiesta Assemblaggio</text>

  <!-- UC13 – extends UC12 -->
  <ellipse cx="660" cy="510" rx="80" ry="24" fill="#ffedd5" stroke="#ea580c" stroke-width="1.5" stroke-dasharray="5,3"/>
  <text x="660" y="506" text-anchor="middle" font-size="10" fill="#1e293b" font-weight="bold">UC13</text>
  <text x="660" y="519" text-anchor="middle" font-size="9.5" fill="#334155">Effettua Pagamento</text>

  <!-- UC14 -->
  <ellipse cx="870" cy="510" rx="80" ry="24" fill="white" stroke="#ea580c" stroke-width="1.5"/>
  <text x="870" y="506" text-anchor="middle" font-size="10" fill="#1e293b" font-weight="bold">UC14</text>
  <text x="870" y="519" text-anchor="middle" font-size="9.5" fill="#334155">Conferma Ordine</text>

  <!-- UC15 -->
  <ellipse cx="560" cy="585" rx="80" ry="24" fill="white" stroke="#ea580c" stroke-width="1.5"/>
  <text x="560" y="581" text-anchor="middle" font-size="10" fill="#1e293b" font-weight="bold">UC15</text>
  <text x="560" y="594" text-anchor="middle" font-size="9.5" fill="#334155">Storico Ordini</text>

  <!-- ═══════════════════════════════════════════════════ -->
  <!-- USE CASES – OPERATORE -->
  <!-- ═══════════════════════════════════════════════════ -->
  <!-- UC16 -->
  <ellipse cx="430" cy="685" rx="85" ry="24" fill="white" stroke="#7e22ce" stroke-width="1.5"/>
  <text x="430" y="681" text-anchor="middle" font-size="10" fill="#1e293b" font-weight="bold">UC16</text>
  <text x="430" y="694" text-anchor="middle" font-size="9.5" fill="#334155">Visualizza Richieste</text>

  <!-- UC17 -->
  <ellipse cx="650" cy="685" rx="80" ry="24" fill="white" stroke="#7e22ce" stroke-width="1.5"/>
  <text x="650" y="681" text-anchor="middle" font-size="10" fill="#1e293b" font-weight="bold">UC17</text>
  <text x="650" y="694" text-anchor="middle" font-size="9.5" fill="#334155">Aggiorna Stato Ordine</text>

  <!-- UC18 – extends UC17 -->
  <ellipse cx="870" cy="685" rx="80" ry="24" fill="#f5f3ff" stroke="#7e22ce" stroke-width="1.5" stroke-dasharray="5,3"/>
  <text x="870" y="681" text-anchor="middle" font-size="10" fill="#1e293b" font-weight="bold">UC18</text>
  <text x="870" y="694" text-anchor="middle" font-size="9.5" fill="#334155">Notifica Avanzamento</text>

  <!-- UC19 -->
  <ellipse cx="540" cy="755" rx="80" ry="24" fill="white" stroke="#7e22ce" stroke-width="1.5"/>
  <text x="540" y="751" text-anchor="middle" font-size="10" fill="#1e293b" font-weight="bold">UC19</text>
  <text x="540" y="764" text-anchor="middle" font-size="9.5" fill="#334155">Gestione Inventario</text>

  <!-- ═══════════════════════════════════════════════════ -->
  <!-- USE CASES – CONSEGNA -->
  <!-- ═══════════════════════════════════════════════════ -->
  <!-- UC20 -->
  <ellipse cx="480" cy="840" rx="85" ry="24" fill="white" stroke="#be123c" stroke-width="1.5"/>
  <text x="480" y="836" text-anchor="middle" font-size="10" fill="#1e293b" font-weight="bold">UC20</text>
  <text x="480" y="849" text-anchor="middle" font-size="9.5" fill="#334155">Tracciamento Spedizione</text>

  <!-- UC21 -->
  <ellipse cx="730" cy="840" rx="80" ry="24" fill="white" stroke="#be123c" stroke-width="1.5"/>
  <text x="730" y="836" text-anchor="middle" font-size="10" fill="#1e293b" font-weight="bold">UC21</text>
  <text x="730" y="849" text-anchor="middle" font-size="9.5" fill="#334155">Conferma Ricezione</text>

  <!-- ═══════════════════════════════════════════════════ -->
  <!-- USE CASES – ADMIN -->
  <!-- ═══════════════════════════════════════════════════ -->
  <!-- UC22 -->
  <ellipse cx="390" cy="945" rx="80" ry="24" fill="white" stroke="#0369a1" stroke-width="1.5"/>
  <text x="390" y="941" text-anchor="middle" font-size="10" fill="#1e293b" font-weight="bold">UC22</text>
  <text x="390" y="954" text-anchor="middle" font-size="9.5" fill="#334155">Gestione Utenti</text>

  <!-- UC23 -->
  <ellipse cx="590" cy="945" rx="80" ry="24" fill="white" stroke="#0369a1" stroke-width="1.5"/>
  <text x="590" y="941" text-anchor="middle" font-size="10" fill="#1e293b" font-weight="bold">UC23</text>
  <text x="590" y="954" text-anchor="middle" font-size="9.5" fill="#334155">Gestione Componenti</text>

  <!-- UC24 -->
  <ellipse cx="800" cy="945" rx="80" ry="24" fill="white" stroke="#0369a1" stroke-width="1.5"/>
  <text x="800" y="941" text-anchor="middle" font-size="10" fill="#1e293b" font-weight="bold">UC24</text>
  <text x="800" y="954" text-anchor="middle" font-size="9.5" fill="#334155">Report Vendite</text>

  <!-- UC25 -->
  <ellipse cx="430" cy="1020" rx="80" ry="24" fill="white" stroke="#0369a1" stroke-width="1.5"/>
  <text x="430" y="1016" text-anchor="middle" font-size="10" fill="#1e293b" font-weight="bold">UC25</text>
  <text x="430" y="1029" text-anchor="middle" font-size="9.5" fill="#334155">Monitoraggio Sistema</text>

  <!-- UC26 -->
  <ellipse cx="700" cy="1020" rx="90" ry="24" fill="white" stroke="#0369a1" stroke-width="1.5"/>
  <text x="700" y="1016" text-anchor="middle" font-size="10" fill="#1e293b" font-weight="bold">UC26</text>
  <text x="700" y="1029" text-anchor="middle" font-size="9.5" fill="#334155">Gestione Regole Compatibilità</text>

  <!-- ═══════════════════════════════════════════════════ -->
  <!-- ATTORI -->
  <!-- ═══════════════════════════════════════════════════ -->

  <!-- UTENTE (sx) -->
  <g transform="translate(100,400)">
    <circle cx="0" cy="-30" r="18" fill="#3A86FF" stroke="#1d4ed8" stroke-width="2"/>
    <line x1="0" y1="-12" x2="0" y2="25" stroke="#1d4ed8" stroke-width="2.5"/>
    <line x1="-22" y1="5" x2="22" y2="5" stroke="#1d4ed8" stroke-width="2.5"/>
    <line x1="0" y1="25" x2="-18" y2="58" stroke="#1d4ed8" stroke-width="2.5"/>
    <line x1="0" y1="25" x2="18" y2="58" stroke="#1d4ed8" stroke-width="2.5"/>
    <text x="0" y="80" text-anchor="middle" font-size="12" font-weight="bold" fill="#1d4ed8">Utente</text>
    <text x="0" y="94" text-anchor="middle" font-size="10" fill="#1d4ed8">(Acquirente)</text>
  </g>

  <!-- OPERATORE (sx basso) -->
  <g transform="translate(100,710)">
    <circle cx="0" cy="-30" r="18" fill="#7e22ce" stroke="#581c87" stroke-width="2"/>
    <line x1="0" y1="-12" x2="0" y2="25" stroke="#581c87" stroke-width="2.5"/>
    <line x1="-22" y1="5" x2="22" y2="5" stroke="#581c87" stroke-width="2.5"/>
    <line x1="0" y1="25" x2="-18" y2="58" stroke="#581c87" stroke-width="2.5"/>
    <line x1="0" y1="25" x2="18" y2="58" stroke="#581c87" stroke-width="2.5"/>
    <text x="0" y="80" text-anchor="middle" font-size="12" font-weight="bold" fill="#581c87">Operatore</text>
    <text x="0" y="94" text-anchor="middle" font-size="10" fill="#581c87">(Tecnico)</text>
  </g>

  <!-- ADMIN (sx fondo) -->
  <g transform="translate(100,990)">
    <circle cx="0" cy="-30" r="18" fill="#0369a1" stroke="#075985" stroke-width="2"/>
    <line x1="0" y1="-12" x2="0" y2="25" stroke="#075985" stroke-width="2.5"/>
    <line x1="-22" y1="5" x2="22" y2="5" stroke="#075985" stroke-width="2.5"/>
    <line x1="0" y1="25" x2="-18" y2="58" stroke="#075985" stroke-width="2.5"/>
    <line x1="0" y1="25" x2="18" y2="58" stroke="#075985" stroke-width="2.5"/>
    <text x="0" y="80" text-anchor="middle" font-size="12" font-weight="bold" fill="#075985">Admin</text>
  </g>

  <!-- SISTEMA PAGAMENTO (dx) -->
  <g transform="translate(1290,510)">
    <rect x="-40" y="-35" width="80" height="55" rx="6" fill="#fef9c3" stroke="#ca8a04" stroke-width="2"/>
    <text x="0" y="-15" text-anchor="middle" font-size="9" fill="#92400e">«external»</text>
    <text x="0" y="0" text-anchor="middle" font-size="11" font-weight="bold" fill="#92400e">Sistema</text>
    <text x="0" y="14" text-anchor="middle" font-size="11" font-weight="bold" fill="#92400e">Pagamento</text>
    <text x="0" y="38" text-anchor="middle" font-size="10" fill="#92400e">💳</text>
  </g>

  <!-- SISTEMA INVENTARIO (dx) -->
  <g transform="translate(1290,330)">
    <rect x="-40" y="-35" width="80" height="55" rx="6" fill="#dcfce7" stroke="#16a34a" stroke-width="2"/>
    <text x="0" y="-15" text-anchor="middle" font-size="9" fill="#14532d">«external»</text>
    <text x="0" y="0" text-anchor="middle" font-size="11" font-weight="bold" fill="#14532d">Sistema</text>
    <text x="0" y="14" text-anchor="middle" font-size="11" font-weight="bold" fill="#14532d">Inventario</text>
    <text x="0" y="38" text-anchor="middle" font-size="10" fill="#14532d">📦</text>
  </g>

  <!-- ═══════════════════════════════════════════════════ -->
  <!-- ASSOCIATION LINES – UTENTE -->
  <!-- ═══════════════════════════════════════════════════ -->
  <!-- Account -->
  <line x1="118" y1="370" x2="358" y2="145" stroke="#3A86FF" stroke-width="1.2" opacity="0.6"/>
  <line x1="118" y1="375" x2="548" y2="145" stroke="#3A86FF" stroke-width="1.2" opacity="0.6"/>
  <line x1="118" y1="378" x2="748" y2="145" stroke="#3A86FF" stroke-width="1.2" opacity="0.6"/>
  <!-- Configurazione -->
  <line x1="118" y1="390" x2="320" y2="255" stroke="#3A86FF" stroke-width="1.2" opacity="0.6"/>
  <line x1="118" y1="395" x2="540" y2="255" stroke="#3A86FF" stroke-width="1.2" opacity="0.6"/>
  <line x1="118" y1="398" x2="320" y2="330" stroke="#3A86FF" stroke-width="1.2" opacity="0.6"/>
  <line x1="118" y1="400" x2="540" y2="330" stroke="#3A86FF" stroke-width="1.2" opacity="0.6"/>
  <line x1="118" y1="402" x2="760" y2="330" stroke="#3A86FF" stroke-width="1.2" opacity="0.6"/>
  <line x1="118" y1="405" x2="350" y2="410" stroke="#3A86FF" stroke-width="1.2" opacity="0.6"/>
  <line x1="118" y1="407" x2="620" y2="410" stroke="#3A86FF" stroke-width="1.2" opacity="0.6"/>
  <!-- Ordine -->
  <line x1="118" y1="415" x2="345" y2="510" stroke="#3A86FF" stroke-width="1.2" opacity="0.6"/>
  <line x1="118" y1="418" x2="480" y2="585" stroke="#3A86FF" stroke-width="1.2" opacity="0.6"/>
  <!-- Consegna -->
  <line x1="118" y1="430" x2="395" y2="840" stroke="#3A86FF" stroke-width="1.2" opacity="0.4"/>
  <line x1="118" y1="432" x2="650" y2="840" stroke="#3A86FF" stroke-width="1.2" opacity="0.4"/>

  <!-- ═══════════════════════════════════════════════════ -->
  <!-- ASSOCIATION LINES – OPERATORE -->
  <!-- ═══════════════════════════════════════════════════ -->
  <line x1="118" y1="680" x2="345" y2="685" stroke="#7e22ce" stroke-width="1.2" opacity="0.6"/>
  <line x1="118" y1="683" x2="570" y2="685" stroke="#7e22ce" stroke-width="1.2" opacity="0.6"/>
  <line x1="118" y1="686" x2="460" y2="755" stroke="#7e22ce" stroke-width="1.2" opacity="0.6"/>

  <!-- ═══════════════════════════════════════════════════ -->
  <!-- ASSOCIATION LINES – ADMIN -->
  <!-- ═══════════════════════════════════════════════════ -->
  <line x1="118" y1="960" x2="310" y2="945" stroke="#0369a1" stroke-width="1.2" opacity="0.6"/>
  <line x1="118" y1="963" x2="510" y2="945" stroke="#0369a1" stroke-width="1.2" opacity="0.6"/>
  <line x1="118" y1="966" x2="720" y2="945" stroke="#0369a1" stroke-width="1.2" opacity="0.6"/>
  <line x1="118" y1="969" x2="350" y2="1020" stroke="#0369a1" stroke-width="1.2" opacity="0.6"/>
  <line x1="118" y1="972" x2="610" y2="1020" stroke="#0369a1" stroke-width="1.2" opacity="0.6"/>

  <!-- ═══════════════════════════════════════════════════ -->
  <!-- ASSOCIATION LINES – EXTERNAL SYSTEMS -->
  <!-- ═══════════════════════════════════════════════════ -->
  <!-- Inventario → UC05, UC07 -->
  <line x1="1250" y1="320" x2="920" y2="262" stroke="#16a34a" stroke-width="1.5" stroke-dasharray="6,3" opacity="0.7"/>
  <line x1="1250" y1="335" x2="920" y2="335" stroke="#16a34a" stroke-width="1.5" stroke-dasharray="6,3" opacity="0.7"/>
  <!-- Pagamento → UC13 -->
  <line x1="1250" y1="510" x2="740" y2="513" stroke="#ca8a04" stroke-width="1.5" stroke-dasharray="6,3" opacity="0.7"/>

  <!-- ═══════════════════════════════════════════════════ -->
  <!-- EXTEND / INCLUDE ARROWS -->
  <!-- ═══════════════════════════════════════════════════ -->
  <!-- UC06 extends UC05 -->
  <line x1="760" y1="255" x2="700" y2="255" stroke="#15803D" stroke-width="1.5" stroke-dasharray="5,3" marker-end="url(#arrowGreen)"/>
  <text x="730" y="248" text-anchor="middle" font-size="8.5" fill="#15803D">«extend»</text>

  <!-- UC13 extends UC12 -->
  <line x1="580" y1="510" x2="515" y2="510" stroke="#ea580c" stroke-width="1.5" stroke-dasharray="5,3" marker-end="url(#arrowOrange)"/>
  <text x="548" y="503" text-anchor="middle" font-size="8.5" fill="#ea580c">«extend»</text>

  <!-- UC18 extends UC17 -->
  <line x1="790" y1="685" x2="730" y2="685" stroke="#7e22ce" stroke-width="1.5" stroke-dasharray="5,3" marker-end="url(#arrowPurple)"/>
  <text x="760" y="678" text-anchor="middle" font-size="8.5" fill="#7e22ce">«extend»</text>

  <!-- UC07 include in UC05 -->
  <line x1="480" y1="306" x2="480" y2="330" stroke="#15803D" stroke-width="1.5" stroke-dasharray="4,3" marker-end="url(#arrowGreen)"/>
  <text x="510" y="322" text-anchor="middle" font-size="8.5" fill="#15803D">«include»</text>

  <!-- ═══════════════════════════════════════════════════ -->
  <!-- ARROW MARKERS -->
  <!-- ═══════════════════════════════════════════════════ -->
  <defs>
    <marker id="arrowGreen" markerWidth="8" markerHeight="8" refX="6" refY="3" orient="auto">
      <path d="M0,0 L0,6 L8,3 z" fill="#15803D"/>
    </marker>
    <marker id="arrowOrange" markerWidth="8" markerHeight="8" refX="6" refY="3" orient="auto">
      <path d="M0,0 L0,6 L8,3 z" fill="#ea580c"/>
    </marker>
    <marker id="arrowPurple" markerWidth="8" markerHeight="8" refX="6" refY="3" orient="auto">
      <path d="M0,0 L0,6 L8,3 z" fill="#7e22ce"/>
    </marker>
  </defs>

  <!-- ═══════════════════════════════════════════════════ -->
  <!-- LEGENDA -->
  <!-- ═══════════════════════════════════════════════════ -->
  <rect x="285" y="1080" width="840" height="32" rx="6" fill="#f1f5f9" stroke="#cbd5e1" stroke-width="1"/>
  <text x="300" y="1099" font-size="10" font-weight="bold" fill="#475569">Legenda:</text>
  <ellipse cx="370" cy="1096" rx="22" ry="9" fill="white" stroke="#475569" stroke-width="1.2"/>
  <text x="398" y="1099" font-size="10" fill="#475569">Use Case</text>
  <ellipse cx="470" cy="1096" rx="22" ry="9" fill="#e0f2fe" stroke="#475569" stroke-width="1.2" stroke-dasharray="4,2"/>
  <text x="498" y="1099" font-size="10" fill="#475569">Extend/Include</text>
  <line x1="610" y1="1096" x2="645" y2="1096" stroke="#475569" stroke-width="1.5" stroke-dasharray="5,3"/>
  <text x="650" y="1099" font-size="10" fill="#475569">Sistema esterno</text>
  <line x1="760" y1="1096" x2="795" y2="1096" stroke="#475569" stroke-width="1.5"/>
  <text x="800" y="1099" font-size="10" fill="#475569">Associazione attore</text>

</svg>