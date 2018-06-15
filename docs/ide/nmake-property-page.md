---
title: Страница свойств NMake (Windows C++) | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCNMakeTool.ReBuildCommandLine
- VC.Project.VCNMakeTool.CleanCommandLine
- VC.Project.VCNMakeTool.Output
- VC.Project.VCNMakeTool.BuildCommandLine
dev_langs:
- C++
helpviewer_keywords:
- NMake property page
ms.assetid: bd20cb52-9f1d-4240-b4fc-4f43205ac94b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f156d69467f00c4c4a62ec84d3b870e2999d7115
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "33327464"
---
# <a name="nmake-property-page"></a>Страница свойств NMake
Страница свойств **NMake** позволяет задать параметры сборки для проектов NMake.  
  
 Дополнительные сведения о проектах NMake см. в разделе [Создание проекта makefile](../ide/creating-a-makefile-project.md). Сведения о проектах makefile не для Windows см. в разделе [Свойства проекта Makefile (Linux C++)](../linux/prop-pages/makefile-linux.md), [Общие свойства проекта (Android C++ Makefile)](/visualstudio/cross-platform/general-makefile-android-prop-page) или [Свойства NMake (Android C++)](/visualstudio/cross-platform/nmake-android-prop-page).
  
 Страница свойств **NMake** содержит указанные ниже свойства.  
  
## <a name="uielement-list"></a>Список элементов пользовательского интерфейса  
 **Командная строка для сборки**  
 Указывает команду, выполняемую при выборе элемента **Собрать** в меню **Сборка**.  
  
 **Командная строка для перестроения всех файлов**  
 Указывает команду, выполняемую при выборе элемента **Перестроить все** в меню **Сборка**.  
  
 **Командная строка для очистки**  
 Указывает команду, выполняемую при выборе элемента **Очистить** в меню **Сборка**.  
  
 **Вывод**  
 Определяет имя файла, который будет содержать выходные данные для командной строки. По умолчанию это имя файла основано на имени проекта.  
  
 **Определения препроцессора**  
 Указывает все определения препроцессора, используемые исходными файлами. Значение по умолчанию определяется текущей платформой и конфигурацией.  
  
 **Путь поиска включаемых файлов**  
 Указывает каталоги, где компилятор ищет включаемые файлы.  
  
 **Принудительно включаемые файлы**  
 Указывает файлы, которые препроцессор автоматически обрабатывает, даже если они не включены в файлы проекта.  
  
 **Путь поиска сборок**  
 Указывает каталоги, где платформа .NET Framework выполняет поиск, пытаясь разрешить сборки .NET.  
  
 **Обязательно используемые сборки**  
 Указывает сборки, которые платформа .NET Framework обрабатывает автоматически.  
  
 **Дополнительные параметры**  
 Указывает дополнительные параметры компилятора для IntelliSense, используемые при анализе файлов C++.  
  
 Сведения о доступе к странице свойств **NMake** см. в разделе [Работа со свойствами проектов](../ide/working-with-project-properties.md).  
  
 Сведения о программном доступе к членам этого объекта см. в разделе <xref:Microsoft.VisualStudio.VCProjectEngine.VCNMakeTool>.  
  
## <a name="see-also"></a>См. также  
 [Страницы свойств](../ide/property-pages-visual-cpp.md)   
 [Практическое руководство. Использование IntelliSense для проекта Makefile](../ide/how-to-enable-intellisense-for-makefile-projects.md)