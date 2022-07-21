# Verde automático

[![estado de compilación](https://github.com/justjavac/auto-green/workflows/ci/badge.svg?branch=master)](https://github.com/justjavac/auto-green/actions )

Mantenga automáticamente el estado de confirmación de GitHub siempre en verde.

> Un compromiso al día mantiene alejada a tu novia.

## Original

Use la función del programador de tareas de GitHub Actions para ejecutar automáticamente un "compromiso de git" a intervalos regulares, y la información del compromiso es "un compromiso al día mantendrá alejada a su novia", inspirado en la pregunta de Zhihu [Cómo hacer que los 365 días sean completamente verdes, sigan adelante GitHub algún tipo de experiencia? ](https://www.zhihu.com/question/34043434/answer/57826281) Respuesta de un usuario anónimo:

> Estuvo todo verde durante más de 200 días, pero a mi novia se le cayó y ha sido verde hasta ahora.

Para conocer los conceptos básicos de Github Action, puede consultar el documento oficial Introducción a Github Actions.

## usar

- Haga clic en el botón **Usar esta plantilla** en la esquina superior derecha para copiar este repositorio de github, **: advertencia: no bifurque, porque la dinámica de su proyecto de bifurcación no se pondrá verde :advertencia:**
- Cambie [líneas 7 y 8 del archivo ci.yml](https://github.com/justjavac/auto-green/blob/master/.github/workflows/ci.yml#L7-L8) para eliminar el archivo . la marca "#".
- Cambie [líneas 19, 20 del archivo ci.yml](https://github.com/justjavac/auto-green/blob/master/.github/workflows/ci.yml#L19-L20) a su cuenta de GitHub y apodos
- (opcional) Puede hacer esto cambiando [línea 8 del archivo ci.yml] (https://github.com/justjavac/auto-green/blob/master/.github/workflows/ci.yml#L8) dar Establecer la frecuencia

La agenda programada tiene 5 campos separados por espacios, cada campo representa una unidad de tiempo.

``` llano
┌──────────────── minutos (0 - 59)
│ ┌──────────────── Horas (0 - 23)
día (1 - 31)
│ │ │ ┌──────────────── Mes (1 - 12 o enero a diciembre)
│ │ │ │ ┌──────────────── Semana de la semana (0 - 6 o SUN-SAT)
│ │ │ │ │
│ │ │ │ │
│ │ │ │ │
* * * * *
```

El significado de cada campo de tiempo:

| símbolo | Descripción Ejemplo |
| ----- | -----------| ------------------------------ ------------|
| ``*'' | Cualquier cantidad | `* * * * *` cada hora cada minuto de cada día |
| `, ` | separador de valores | `1,3,4,7 * * * *` cada hora 1 3 4 7 minutos |
| `-` | Gama | `1-6 * * * *` 1-6 minutos por hora |
| `/` | Cada | `*/15 * * * *` cada 15 minutos |

**NOTA**: Debido al límite de acciones de GitHub, si se establece en "* * * * *", la frecuencia de ejecución real es cada 5 minutos.

## Licencia

[auto-green](https://github.com/justjavac/auto-green) se publica bajo la licencia MIT. Consulte el archivo adjunto [LICENCIA](./LICENCIA) para obtener más detalles.
