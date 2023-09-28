# Web3Invest Network Architecture

![Rendu PlantUML](https://www.plantuml.com/plantuml/png/ZP4zJyCm48Rt_8eZOYpDH_a0gLGTW8s9iKN8YQ-9LTUsRASfglhVgLDB62MH6A8evpi_p-LT6akqRNOykcAYv0r5cClDXfMOVA3UepO9KOgpabWcnPVfQelnPaeiAOZ1ySuNt9zV9Z4jisMzY2BHKaOgE4O00cqhzHRUD68X3rqDW52gqHXuXZXxogVP_UCqc-R9NHftnwNaKhj3HJXM6b5SwXS0h8BnLrkZFaCWZoTWQgBGLOMaUFwcQ4hDbDlJLUVNtd0jmAeRpiGs_kmkhhHi5BHOUBzn1G2AUxV8eCHi0h_xp1u6bFfE0s6iXQTuFG2b9HsbPY7rDkrJ_mlr54yzHUu9Cdmdng9sLneu_Wtg6pcNRPXITD56WqINTPfci1fCFUlxXfbiU7FeXy9PLTk2D-X3wTh66Na-m0W7yx71GCxF1R_c52rHq6R7Vm00)

```plantuml
@startuml
!include <office/Servers/application_server>
!include <office/Servers/database_server>
!include <office/Devices/switch>

nwdiag {
  network Freebox {
    address = "192.168.1.2/50"
    color = "palegreen"
    switch [address = "Ethernet 2", shape = "node", description = "<$switch>\n tp-link"]
    group web {
      color = "palegreen"
      devbox [address = "Ethernet 3, 192.168.1.37", shape = "node",  description = "<$application_server>\n devbox"]
      prodbox [address = "Ethernet 1, 192.168.1.40", shape = "node", description = "<$application_server>\n prodbox"]
    }
  }

  network Masternodes {
    color = "yellow"
    switch
    presearch001 [address = "192.168.1.10", shape = "node"]
    group flux {
      color = "lightblue"
      flux001 [address = "192.168.1.22", shape = "node"]
      flux002 [address = "192.168.1.20", shape ="node"]
    }
  }
}
@enduml
```

