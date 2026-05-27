# 🔗 Dependencias - Biblioteca Digital v1.0

## Dependencias Finish-to-Start (FS)

| Tarea | Depende de | Justificación |
|-------|-----------|--------------|
| A2 | A1 | No se registran riesgos sin plan aprobado |
| A3 | A1 | El ERD parte del alcance definido en el plan |
| A4 | A3 | El esquema BD requiere el ERD finalizado |
| A5 | A3 | La API se basa en el modelo de datos |
| A6 | A5 | El diagrama C4 describe los componentes de la API |
| A7 | A4, A5 | El CRUD necesita BD + contrato API definidos |
| A8 | A7 | El validador ISBN se integra al módulo de libros |
| A9 | A4, A5 | La autenticación necesita BD + API definidas |
| A10 | A9 | La gestión de lectores depende del sistema de auth |
| A11 | A7, A9 | La disponibilidad cruza módulo libros y usuarios |
| A12 | A11 | El flujo préstamo/devolución requiere disponibilidad |
| A13 | A12 | Las notificaciones se disparan desde el flujo de préstamo |
| A14 | A8, A10, A13 | Las pruebas requieren todos los módulos completos |
| A15 | A14 | UAT solo después de pruebas técnicas aprobadas |
| A16 | A15 | Infraestructura se configura con producto validado |
| A17 | A16 | Documentación técnica sobre entorno estable |
| A18 | A17 | Handover requiere documentación completa |
| A19 | A18 | Cierre después de transferencia a operaciones |

## 🕸️ Red de Dependencias (Mermaid)

```mermaid
graph LR
    A1[A1: Plan] --> A2[A2: Riesgos]
    A1 --> A3[A3: ERD]
    A3 --> A4[A4: Esquema BD]
    A3 --> A5[A5: Swagger]
    A5 --> A6[A6: C4]
    A4 --> A7[A7: CRUD Libros]
    A5 --> A7
    A7 --> A8[A8: ISBN]
    A4 --> A9[A9: Auth]
    A5 --> A9
    A9 --> A10[A10: Lectores]
    A7 --> A11[A11: Disponibilidad]
    A9 --> A11
    A11 --> A12[A12: Préstamo/Dev.]
    A12 --> A13[A13: Notificaciones]
    A8 --> A14[A14: Unit Tests]
    A10 --> A14
    A13 --> A14
    A14 --> A15[A15: UAT]
    A15 --> A16[A16: Infraestructura]
    A16 --> A17[A17: Docs técnica]
    A17 --> A18[A18: Handover]
    A18 --> A19[A19: Cierre]
```