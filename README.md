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

### 4. **Ceedling**
Para realizar testing unitario se utiliza la herramienta Ceedling.
Esta no está disponible directamente en Windows, pero puede instalarse fácilmente a través de WSL (Ubuntu).

Instalación:

Ejecuta los siguientes comandos dentro de la terminal de WSL:
- Instalación de Ruby (requerido por Ceedling) y Gcovr (para reportes de cobertura)

  sudo apt-get install ruby gcovr

- Instalación de Ceedling mediante RubyGems

  sudo gem install ceedling

Dentro del repositorio, puedes crear un nuevo proyecto de Ceedling de dos formas:
- Crear un proyecto en una nueva carpeta:

  ceedling new "nombre_carpeta"

- Crear el proyecto en la carpeta actual:

  ceedling new .

Estos comandos generan automáticamente las carpetas y archivos por defecto:

  src/

  test/support/

  project.yml

Nota importante: en este repositorio ya existe el archivo project.yml, por lo que no es necesario crear un nuevo proyecto Ceedling. Simplemente coloca tus archivos de prueba dentro de la carpeta test/ — no deben crearse en otra ubicación.

---

## Uso del repositorio

Este repositorio utiliza las siguientes herramientas:

1. [clang-format](https://clang.llvm.org/docs/ClangFormat.html) para el mantenimiento de formato del código escrito en lenguaje C
2. [pre-commit](https://pre-commit.com) para validaciones generales de formato del repositorio
3. [ceedling](https://www.throwtheswitch.org/ceedling) para ejecutar las pruebas unitarias en forma automatizada
4. [lcov]() para generar los informes de cobertura de las pruebas unitarias

Después de clonar el repositorio usted debería ejecutar el siguiente comando:

```
pre-commit install
```

Para ejecutar las pruebas unitarias se utiliza el siguiente comando:

```
ceedling test:all
```

Para generar el informe de cobertura de las pruebas se utiliza el siguiente comando:

```
ceedling clobber gcov:all
```

Para generar la documentación del proyecto se utiliza el siguiente comando:

```
doxygen doxyfile

```

Nota: Los reportes de cobertura por defecto se guardan en la carpeta build/artifacts/gcov/gcovr/GcovCoverageCobertura.html y los reportes de test se guardan en la carpeta build/artifacts/gcov/junit_tests_report.html. La documentacion con doxygen se guarda en la carpeta build/doc/html/index.html.
