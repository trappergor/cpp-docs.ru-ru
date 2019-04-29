---
title: Страница свойств NMake (Windows C++) | Документы Майкрософт
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCNMakeTool.ReBuildCommandLine
- VC.Project.VCNMakeTool.CleanCommandLine
- VC.Project.VCNMakeTool.Output
- VC.Project.VCNMakeTool.BuildCommandLine
helpviewer_keywords:
- NMake property page
ms.assetid: bd20cb52-9f1d-4240-b4fc-4f43205ac94b
ms.openlocfilehash: c0dbe537635fe6698f814f3d8456f0caa9c8c796
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320608"
---
# <a name="nmake-property-page"></a>Страница свойств NMake

Страница свойств **NMake** позволяет задать параметры сборки для проектов NMake. ((NMAKE) является реализацией Майкрософт [сделать](https://wikipedia.org/wiki/Make_(software)).)

Дополнительные сведения о проектах NMake см. в разделе [Создание проекта makefile](creating-a-makefile-project.md). Для проектов MakeFile, отличных от Windows, см. в разделе [свойства проекта MakeFile (Linux C++)](../../linux/prop-pages/makefile-linux.md), [общие свойства проекта (Android C++ Makefile)](/visualstudio/cross-platform/general-makefile-android-prop-page) или [свойства NMake (Android C++)](/visualstudio/cross-platform/nmake-android-prop-page).

Страница свойств **NMake** содержит указанные ниже свойства.

## <a name="uielement-list"></a>Список элементов пользовательского интерфейса

- **Командная строка для сборки**

   Указывает команду, выполняемую при выборе элемента **Собрать** в меню **Сборка**.

- **Командная строка для перестроения всех файлов**

   Указывает команду, выполняемую при выборе элемента **Перестроить все** в меню **Сборка**.

- **Командная строка для очистки**

   Указывает команду, выполняемую при выборе элемента **Очистить** в меню **Сборка**.

- **Вывод**

   Определяет имя файла, который будет содержать выходные данные для командной строки. По умолчанию это имя файла основано на имени проекта.

- **Определения препроцессора**

   Указывает все определения препроцессора, используемые исходными файлами. Значение по умолчанию определяется текущей платформой и конфигурацией.

- **Путь поиска включаемых файлов**

   Указывает каталоги, где компилятор ищет включаемые файлы.

- **Принудительно включаемые файлы**

   Указывает файлы, которые препроцессор автоматически обрабатывает, даже если они не включены в файлы проекта.

- **Путь поиска сборок**

   Указывает каталоги, где платформа .NET Framework выполняет поиск, пытаясь разрешить сборки .NET.

- **Обязательно используемые сборки**

   Указывает сборки, которые платформа .NET Framework обрабатывает автоматически.

- **Дополнительные параметры**

   Указывает дополнительные параметры компилятора для IntelliSense, используемые при анализе файлов C++.

Сведения о доступе к **NMake** страницу свойств, см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

Сведения о программном доступе к членам этого объекта см. в разделе <xref:Microsoft.VisualStudio.VCProjectEngine.VCNMakeTool>.

## <a name="see-also"></a>См. также

[Справочник по страницам свойств проекта C++](property-pages-visual-cpp.md)<br>
