## 📘 Documentación del código

### 🔧 Requisitos previos

Para comenzar a trabajar con este proyecto en C para STM32, es necesario instalar las siguientes herramientas:

---

### 1. **Clang-Format**

- Descarga **Clang-Format** desde la página oficial de LLVM:
  [https://github.com/llvm/llvm-project/releases/tag/llvmorg-18.1.8](https://github.com/llvm/llvm-project/releases/tag/llvmorg-18.1.8)
- En este proyecto se utilizó la versión **LLVM-18.1.8-win64.exe**.
- Se recomienda instalar la extensión de **VS Code**:
  **Clang-Format** — desarrollada por *Xaver Hellauer*.
  Esta extensión permite aplicar formato automáticamente al guardar los archivos fuente.

---

### 2. **Pre-commit**

- Para usar **pre-commit** en Windows es necesario tener instalados **Python**, **pip** y **Git**, y asegurarse de que estén agregados al **PATH** del sistema.
- Luego, desde la terminal (CMD o PowerShell), instala pre-commit con "pip install pre-commit"
- En este proyecto se utilizó la versión pre-commit 4.3.0.
- También se recomienda instalar la extensión de VS Code:
  GitHub Actions, para ejecutar automáticamente los hooks de pre-commit cada vez que se haga un pull request a la rama main.

---

### 3. **Doxygen**

- Descarga e instala Doxygen desde: [https://www.doxygen.nl/download.html](https://www.doxygen.nl/download.html)

- Agrega Doxygen al PATH del sistema para poder ejecutarlo desde la terminal.
- En VS Code se puede utilizar la extensión:
  Doxygen Documentation Generator — desarrollada por Christoph Schlosser, que facilita la creación de comentarios compatibles con Doxygen.

---

## Uso del repositorio

Este repositorio utiliza [pre-commit](https://pre-commit.com) para validaciones de formato. Para trabajar con el mismo usted debería tener instalado:

1. pre-commit (https://pre-commit.com/#install)

Después de clonar el repositorio usted debería ejecutar el siguiente comando:

```
pre-commit install
```

Para generar la documentación del proyecto se utiliza el siguiente comando:

```
doxygen doxyfile
```
Nota: Los archivos HTML resultantes se encontrarán dentro del directorio configurado en el archivo doxyfile (por ejemplo: build/doc/html/index.html).
