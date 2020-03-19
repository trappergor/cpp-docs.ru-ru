---
title: Общие свойства проекта (Android C++)
ms.date: 10/23/2017
ms.assetid: 65f4868b-b864-4989-a275-1e51869ef599
f1_keywords:
- VC.Project.VCConfiguration.Android.OutputDirectory
- VC.Project.VCConfiguration.Android.IntermediateDirectory
- VC.Project.VCConfiguration.Android.TargetName
- VC.Project.VCConfiguration.Android.TargetExt
- VC.Project.VCConfiguration.Android.DeleteExtensionsOnClean
- VC.Project.VCConfiguration.Android.BuildLogFile
- VC.Project.VCConfiguration.Android.PlatformToolset
- VC.Project.VCConfiguration.Android.ConfigurationType
- VC.Project.VCConfiguration.UseOfSTL
- VC.Project.VCConfiguration.ThumbMode
ms.openlocfilehash: 78f6df8286151b61ed026cc6b5170ff3508295d4
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79470271"
---
# <a name="general-project-properties-android-c"></a>Общие свойства проекта (Android C++)

| Свойство | Description | Варианты |
|--|--|--|
| Выходной каталог | Указывает относительный путь к выходному каталогу файлов; может включать в себя переменные среды. |
| Промежуточный каталог | Указывает относительный путь к промежуточному каталогу файлов; может включать в себя переменные среды. |
| Имя цели | Указывает имя файла, создаваемого этим проектом. |
| Расширение цели | Указывает расширение файла, создаваемое этим проектом. (Пример: *EXE* или *DLL*.) |
| Расширения для удаления при очистке | Спецификация из подстановочных знаков (разделитель — точка с запятой), определяющая, какие файлы в промежуточном каталоге нужно удалять при очистке или перестроении. |
| Файл журнала сборки | Определяет файл журнала сборки, в который будет вестись запись, если ведение журнала включено. |
| Набор инструментов платформы | Задает набор инструментов, используемый для сборки текущей конфигурации; если не указан, используется набор инструментов по умолчанию |
| Тип конфигурации | Определяет тип выходных данных, создаваемых этой конфигурацией. | **Динамическая библиотека (.so)**  — динамическая библиотека ( *.so*)<br>**Статическая библиотека (.a)** — статическая библиотека ( *.a*)<br>**Служебная программа** — служебная программа<br>**Makefile** — файл Makefile<br> |
| Целевой уровень API | Целевой уровень API NDK Android для этой конфигурации. |
| Использование STL | Указывает, какую стандартную библиотеку C++ следует использовать для этой конфигурации. | **Минимальная библиотека среды выполнения C++ (система)**<br>**Статическая библиотека среды выполнения C++ (gabi++_static)**<br>**Общая библиотека среды выполнения C++ (gabi++_shared)**<br>**Статическая библиотека среды выполнения STLport (stlport_static)**<br>**Общая библиотека среды выполнения STLport (stlport_shared)**<br>**Статическая библиотека GNU STL (gnustl_static)**<br>**Общая библиотека GNU STL (gnustl_shared)**<br>**Статическая библиотека LLVM libc++ (c++_static)**<br>**Общая библиотека LLVM libc++ (c++_shared)**<br> |
| Режим Thumb | Создайте код, выполняемый для микроархитектуры Thumb. Применимо только к архитектуре ARM. | **Thumb**<br>**ARM**<br>**Отключено**<br> |
