---
title: Страница свойств NMake (Windows C++) | Документы Microsoft
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
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="nmake-property-page"></a>Страница свойств NMake
**NMake** страница свойств позволяет задать параметры построения для проектов NMake.  
  
 Дополнительные сведения о проектах NMake см. в разделе [Создание проекта Makefile](../ide/creating-a-makefile-project.md). Non_Windows проектов MakeFile. в разделе [свойства проекта MakeFile (Linux C++)](../linux/prop-pages/makefile-linux.md), [общие свойства проекта (Android C++ Makefile)](/visualstudio/cross-platform/general-makefile-android-prop-page) или [NMake свойства (Android C++)](/visualstudio/cross-platform/nmake-android-prop-page).
  
 **NMake** страница свойств содержит следующие свойства.  
  
## <a name="uielement-list"></a>Список элементов пользовательского интерфейса  
 **Командная строка построения**  
 Указывает команду для запуска при **построения** щелчке **построения** меню.  
  
 **Перестроение всех командной строки**  
 Указывает команду для запуска при **перестроить все** щелчке **построения** меню.  
  
 **Командная строка очистки**  
 Указывает команду для запуска при **Очистить** щелчке **построения** меню.  
  
 **Вывод**  
 Задает имя файла, который будет содержать вывод командной строки. По умолчанию это имя файла основано на имени проекта.  
  
 **Определения препроцессора**  
 Задает все определения препроцессора, используемые в исходных файлах. Значение по умолчанию определяется текущей платформой и конфигурацией.  
  
 **Путь поиска включаемых файлов**  
 Задает каталоги, где компилятор выполняет поиск включаемых файлов.  
  
 **Принудительно включает**  
 Указывает файлы, препроцессор автоматически обрабатывает, даже если они не включаются в файлах проекта.  
  
 **Путь поиска сборок**  
 Указывает каталоги, где .NET Framework выполняет при его предпринимается попытка расшифровать сборок .NET.  
  
 **Принудительное использование сборок**  
 Указывает сборки, которые .NET Framework автоматически обрабатывает.  
  
 **Дополнительные параметры**  
 Указывает дополнительные параметры компилятора для IntelliSense для использования при синтаксическом анализе файлов C++.  
  
 Сведения о доступе к **NMake** страницу свойств в разделе [работа со свойствами проекта](../ide/working-with-project-properties.md).  
  
 Сведения о доступе к членам этого объекта см. в разделе <xref:Microsoft.VisualStudio.VCProjectEngine.VCNMakeTool>.  
  
## <a name="see-also"></a>См. также  
 [Страницы свойств](../ide/property-pages-visual-cpp.md)   
 [Практическое руководство. Использование IntelliSense для проекта Makefile](../ide/how-to-enable-intellisense-for-makefile-projects.md)