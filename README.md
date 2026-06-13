# Al Día — tasas de referencia

Fuente de datos en vivo de las tasas que muestra la app **Al Día** (cuentas remuneradas y CDT en Colombia).

- **URL que consume la app:** https://jcandrade25.github.io/aldia-rates/rates.json
- **Archivo:** [`rates.json`](rates.json)

## Cómo actualizar las tasas

1. Abre [`rates.json`](rates.json) en GitHub y pulsa el lápiz (✏️) para editar — se puede desde el navegador o el celular.
2. Cambia el `tasa_ea` (porcentaje **E.A.**, efectiva anual) de la entidad, o agrega/quita objetos de la lista `rates`.
3. **Sube la fecha `"updated"`** (formato `AAAA-MM-DD`) a la fecha de hoy. Importante: las correcciones manuales que el usuario haya hecho dentro de la app se descartan si son anteriores a `updated`, de modo que los datos nuevos mandan.
4. Confirma el cambio (commit). GitHub Pages republica en ~1 minuto y la app toma el valor nuevo en su siguiente apertura. Sin conexión, la app usa la última versión guardada y, si nunca la descargó, la copia incluida en la app.

## Esquema de cada tasa

```json
{
  "entidad": "Nu",                 // nombre de la entidad
  "producto": "Cajitas de ahorro", // nombre del producto
  "tipo": "cuenta",                // "cuenta" o "cdt"
  "plazo": "360 días",             // solo CDT; "" para cuentas
  "tasa_ea": 9.25,                  // porcentaje E.A.
  "bajo_monto": false,              // true = depósito de bajo monto (badge 4x1000)
  "color": "#820AD1",              // color de marca (hex)
  "condiciones": "…",              // letra chica
  "verificado": "2026-06-12",      // fecha en que se verificó esa tasa
  "fuente": "Nu"                   // de dónde se tomó
}
```

Las tasas son referenciales; cada entidad puede cambiarlas sin aviso.
