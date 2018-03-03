---
title: "Страница свойств NMake (Windows C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7cc9f6dc7c5fec4a184ed189cfaae230df3f1e9e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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