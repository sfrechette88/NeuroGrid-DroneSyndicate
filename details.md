## Arborescence de localisation

Métropole : une seule, NeuroGrid
Districts : 1 Métropole comporte 16 Districts
Secteurs : 1 District comporte 16 Secteurs
Quartiers : 1 Secteur comporte 16 Quartiers
Blocs : 1 Quartir comporte 16 Blocs

Pour adresser chaque localisation, on utilise la notation hexadécimale.
Le premier Disctrict sera 0x0, le deuxième 0x1, etc..
Le premier Secteur du deuxième District sera : 0x10
Le premier Quartier du Secteur 3 du District 4 sera : 0x430
Et le Bloc 8 (le 9e) du Quartier 3 (le 4e) du Secteur 6 (le 7e) du District A (le 10e) sera : 0xA638

Ca sera un peut comme la position géographique de tout. On peut donner une position à 3 charactères. Exemple : 0xA46.
Cela indique uniquement le Quartier sans mentionner le Bloc.

## Nommage des différentes localisations
```
{
  "metropole": {
    "name": "NeuroGrid",
    "districts": [
      {
        "name": "0x0 - CoreNet",
        "desc": "Primary nexus of governance, consortium HQs, and backbone data hubs.",
        "sectors": [
          "0x00 - UltraLine",
          "0x01 - QuantumThread",
          "0x02 - FrameTrack",
          "0x03 - VoltDrift",
          "0x04 - LogicFabric",
          "0x05 - CyberVector",
          "0x06 - TraceTrack",
          "0x07 - SubVector",
          "0x08 - CoreNode",
          "0x09 - VectorTrack",
          "0x0A - DarkEngine",
          "0x0B - TraceField",
          "0x0C - VoltPort",
          "0x0D - CyberLoop",
          "0x0E - FrameHaven",
          "0x0F - CoreStack"
        ]
      },
      {
        "name": "0x1 - VoltEdge",
        "desc": "Energy corridors, high-capacity substations, and drone charge stacks.",
        "sectors": [
          "0x10 - GridLoop",
          "0x11 - VoidChannel",
          "0x12 - QuantumVault",
          "0x13 - VectorAxis",
          "0x14 - VantaWay",
          "0x15 - IonWay",
          "0x16 - CryoSpan",
          "0x17 - DataField",
          "0x18 - CloudFrame",
          "0x19 - FluxGate",
          "0x1A - SubChannel",
          "0x1B - DarkThread",
          "0x1C - LogicAxis",
          "0x1D - ParaWay",
          "0x1E - LogicAnchor",
          "0x1F - InfraNode"
        ]
      },
      {
        "name": "0x2 - DataForge",
        "desc": "Repurposed data-centers fused with workshops, logistics, and housing.",
        "sectors": [
          "0x20 - MacroPort",
          "0x21 - CryptoSector",
          "0x22 - VectorEngine",
          "0x23 - VantaArray",
          "0x24 - DarkRun",
          "0x25 - NoirThread",
          "0x26 - UltraStack",
          "0x27 - VoidAnchor",
          "0x28 - ForgeLayer",
          "0x29 - TraceAxis",
          "0x2A - ThreadDrive",
          "0x2B - DataBloom",
          "0x2C - CloudStack",
          "0x2D - FluxStack",
          "0x2E - NoirBloom",
          "0x2F - UltraAxis"
        ]
      },
      {
        "name": "0x3 - NeonArc",
        "desc": "Commercial ribbons, holograph boulevards, and high-traffic night lanes.",
        "sectors": [
          "0x30 - GateDelta",
          "0x31 - PulseArray",
          "0x32 - StackLink",
          "0x33 - CyberLink",
          "0x34 - MicroArray",
          "0x35 - ColdRidge",
          "0x36 - VantaBloom",
          "0x37 - DataPort",
          "0x38 - VoltSector",
          "0x39 - FrameDrift",
          "0x3A - SignalLoop",
          "0x3B - SubCircuit",
          "0x3C - CryptoPrime",
          "0x3D - VantaGate",
          "0x3E - HyperAxis",
          "0x3F - MetaThread"
        ]
      },
      {
        "name": "0x4 - CryoStack",
        "desc": "Cooling towers, wet labs, and bio-cyber research platforms.",
        "sectors": [
          "0x40 - ForgeWay",
          "0x41 - MicroVault",
          "0x42 - ColdDrift",
          "0x43 - DarkLayer",
          "0x44 - SubSector",
          "0x45 - VectorPrime",
          "0x46 - DarkWay",
          "0x47 - FluxPort",
          "0x48 - OverVista",
          "0x49 - LoopTrack",
          "0x4A - PulseWorks",
          "0x4B - GateCircuit",
          "0x4C - PhaseDrift",
          "0x4D - ColdAxis",
          "0x4E - MacroAnchor",
          "0x4F - GridCore"
        ]
      },
      {
        "name": "0x5 - SysLoop",
        "desc": "Automated logistics loop: internal metros, sorters, and parcel grids.",
        "sectors": [
          "0x50 - CyberPort",
          "0x51 - VantaStack",
          "0x52 - MetaAnchor",
          "0x53 - NanoFrame",
          "0x54 - FrameDelta",
          "0x55 - SubArray",
          "0x56 - PhaseCore",
          "0x57 - ForgeCircuit",
          "0x58 - VoltAnchor",
          "0x59 - FluxLoop",
          "0x5A - MetaCore",
          "0x5B - HyperField",
          "0x5C - IonBridge",
          "0x5D - MetaRun",
          "0x5E - LogicDelta",
          "0x5F - GateReach"
        ]
      },
      {
        "name": "0x6 - ByteHaven",
        "desc": "Makers, hackers, printfarms; always-on studios and back-alley netbars.",
        "sectors": [
          "0x60 - LoopFrame",
          "0x61 - NoirCircuit",
          "0x62 - FrameAnchor",
          "0x63 - HyperVector",
          "0x64 - DarkVista",
          "0x65 - SignalThread",
          "0x66 - NoirAxis",
          "0x67 - MacroAxis",
          "0x68 - InfraAnchor",
          "0x69 - CyberAxis",
          "0x6A - NodeStack",
          "0x6B - NoirStack",
          "0x6C - CyberVista",
          "0x6D - MetaSector",
          "0x6E - SubLayer",
          "0x6F - DataGate"
        ]
      },
      {
        "name": "0x7 - OverLink",
        "desc": "Raised throughways, relay masts, and citywide line-of-sight links.",
        "sectors": [
          "0x70 - GridField",
          "0x71 - SubGate",
          "0x72 - HyperRidge",
          "0x73 - ParaField",
          "0x74 - TraceDrive",
          "0x75 - Echoline",
          "0x76 - Coldline",
          "0x77 - StackSpan",
          "0x78 - DriftBlock",
          "0x79 - VantaCore",
          "0x7A - VoltMatrix",
          "0x7B - FrameCircuit",
          "0x7C - VoidRun",
          "0x7D - CoreBridge",
          "0x7E - PulseSpan",
          "0x7F - StackChannel"
        ]
      },
      {
        "name": "0x8 - GridFall",
        "desc": "Fractured network tier; semi-abandoned scaffolds rich in salvage.",
        "sectors": [
          "0x80 - Gridline",
          "0x81 - DataLink",
          "0x82 - StackReach",
          "0x83 - LoopLayer",
          "0x84 - DarkSpire",
          "0x85 - IonFabric",
          "0x86 - NodeChannel",
          "0x87 - IonNode",
          "0x88 - IonSpire",
          "0x89 - ColdTrack",
          "0x8A - CyberCore",
          "0x8B - FrameMatrix",
          "0x8C - PhaseThread",
          "0x8D - PulseCircuit",
          "0x8E - CloudDrive",
          "0x8F - EchoVault"
        ]
      },
      {
        "name": "0x9 - MechSpire",
        "desc": "Vertical robotics, hard-implant clinics, and assembly shafts.",
        "sectors": [
          "0x90 - FluxRidge",
          "0x91 - NanoRidge",
          "0x92 - OverDrive",
          "0x93 - CoreBloom",
          "0x94 - DarkDrift",
          "0x95 - VantaCircuit",
          "0x96 - GateField",
          "0x97 - Coreline",
          "0x98 - InfraAxis",
          "0x99 - TraceBridge",
          "0x9A - ColdWay",
          "0x9B - NanoStack",
          "0x9C - QuantumCircuit",
          "0x9D - LoopBloom",
          "0x9E - FrameNode",
          "0x9F - MacroHaven"
        ]
      },
      {
        "name": "0xA - PulseGate",
        "desc": "Interchange for transport, energy, and data; the heartbeat junction.",
        "sectors": [
          "0xA0 - DataRun",
          "0xA1 - StackArray",
          "0xA2 - CyberSpan",
          "0xA3 - NoirCore",
          "0xA4 - SignalVista",
          "0xA5 - Hyperlane",
          "0xA6 - NoirSpan",
          "0xA7 - ParaDrift",
          "0xA8 - PulseDelta",
          "0xA9 - MetaLoop",
          "0xAA - PulsePrime",
          "0xAB - CloudCircuit",
          "0xAC - DarkReach",
          "0xAD - SubFabric",
          "0xAE - VectorFrame",
          "0xAF - QuantumStack"
        ]
      },
      {
        "name": "0xB - IronVeil",
        "desc": "Heavy maintenance, alloy yards, modular depots, and sealed bays.",
        "sectors": [
          "0xB0 - Darkline",
          "0xB1 - LoopHaven",
          "0xB2 - ForgeReach",
          "0xB3 - MetaFabric",
          "0xB4 - TraceVault",
          "0xB5 - StackBloom",
          "0xB6 - ThreadSector",
          "0xB7 - DarkAxis",
          "0xB8 - NanoMatrix",
          "0xB9 - SubLine",
          "0xBA - CryptoVault",
          "0xBB - EchoEngine",
          "0xBC - ForgeDock",
          "0xBD - GateDrift",
          "0xBE - NeoDelta",
          "0xBF - NeoWay"
        ]
      },
      {
        "name": "0xC - Synthora",
        "desc": "Bio-synthetic testbeds, AR dens, and perception engineering labs.",
        "sectors": [
          "0xC0 - MetaHaven",
          "0xC1 - SignalPort",
          "0xC2 - IonRidge",
          "0xC3 - FrameRun",
          "0xC4 - GridSpire",
          "0xC5 - HyperChannel",
          "0xC6 - VoidCross",
          "0xC7 - CloudLoop",
          "0xC8 - NoirNode",
          "0xC9 - CryptoLoop",
          "0xCA - CoreWay",
          "0xCB - PhaseChannel",
          "0xCC - FluxNode",
          "0xCD - MetaCircuit",
          "0xCE - DataVault",
          "0xCF - VectorWay"
        ]
      },
      {
        "name": "0xD - CloudRift",
        "desc": "Suspended upperworks, artificial cloud layers, altitude servers.",
        "sectors": [
          "0xD0 - GateSpire",
          "0xD1 - FrameDrive",
          "0xD2 - UltraFabric",
          "0xD3 - HyperHaven",
          "0xD4 - SignalWay",
          "0xD5 - ForgeVault",
          "0xD6 - PhaseWorks",
          "0xD7 - IonRun",
          "0xD8 - GridSpan",
          "0xD9 - EchoNode",
          "0xDA - OverRidge",
          "0xDB - NeoLoop",
          "0xDC - StackPort",
          "0xDD - UltraDelta",
          "0xDE - SubNet",
          "0xDF - MacroGate"
        ]
      },
      {
        "name": "0xE - NoirBand",
        "desc": "Darknet interchanges, obfuscated routes, and restricted access points.",
        "sectors": [
          "0xE0 - MacroStack",
          "0xE1 - FrameVector",
          "0xE2 - NeoFrame",
          "0xE3 - NodeRidge",
          "0xE4 - VantaDrive",
          "0xE5 - LogicNode",
          "0xE6 - LoopWorks",
          "0xE7 - ParaWorks",
          "0xE8 - MacroDrive",
          "0xE9 - Phaseline",
          "0xEA - HyperEngine",
          "0xEB - PhaseStack",
          "0xEC - OverVault",
          "0xED - MacroEngine",
          "0xEE - ColdLink",
          "0xEF - CloudAxis"
        ]
      },
      {
        "name": "0xF - DustFrame",
        "desc": "Edge redevelopment, stripped frameworks, and contested rebuild zones.",
        "sectors": [
          "0xF0 - NoirWay",
          "0xF1 - NodeEngine",
          "0xF2 - GateLine",
          "0xF3 - CloudAnchor",
          "0xF4 - CryptoVector",
          "0xF5 - PulseAnchor",
          "0xF6 - CoreArray",
          "0xF7 - DataLoop",
          "0xF8 - GateVector",
          "0xF9 - IonPort",
          "0xFA - HyperGate",
          "0xFB - ForgeSpan",
          "0xFC - VoltEngine",
          "0xFD - MacroLink",
          "0xFE - ThreadBloom",
          "0xFF - HyperLayer"
        ]
      }
    ]
  }
}
```
