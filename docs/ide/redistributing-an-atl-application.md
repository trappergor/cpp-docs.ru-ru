---
title: "Распространение приложения ATL | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ATL, redistributing
- redistributing ATL
- redistributing OLE DB templates
- OLE DB templates, redistributing
ms.assetid: 9a696b22-2345-43ec-826b-be7cb8cfd676
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3a9e4259c70aff53252cd91db217a96d9d5480a7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="redistributing-an-atl-application"></a>Повторное распространение приложения ATL
Начиная с версии Visual Studio 2012 в библиотеку Active Template Library (ATL) входят только заголовки. Проекты ATL не имеют динамической компоновки с ATL. Распространяемая библиотека ATL не требуется.  
  
 При распространении исполняемого приложения ATL необходимо зарегистрировать файл EXE (и все элементы управления внутри него), выполнив следующую команду:  
  
```  
filename /regserver  
```  
  
 где `filename` — это имя исполняемого файла.  
  
 В Visual Studio 2010 проект ATL можно собирать для конфигурации MinDependency или MinSize. Конфигурация MinDependency получается при установке **использование ATL** свойства **статическая компоновка с ATL** на **Общие** странице свойств, а также набор  **Библиотека времени выполнения** свойства **несколькими потоками (/ MT)** на **создания кода** страницы свойств (папка C/C++).  
  
 Конфигурация MinSize получается при установке **использование ATL** свойства **динамическая компоновка с ATL** на **Общие** на странице свойств или набор **среды выполнения Библиотека** свойства **Многопоточная DLL (/ MD)** на **создания кода** страницы свойств (папка C/C++).  
  
 Конфигурация MinSize позволяет создать выходной файл, но требует библиотек ATL100.dll и Msvcr100.dll (Если вы выбрали **Многопоточная DLL (/ MD)** параметр) на конечном компьютере. Для работы всех функции ATL библиотека ATL100.dll должна быть зарегистрирована на целевом компьютере. Библиотека ATL100.dll содержит экспортированные данные в формате ANSI и Юникод.  
  
 При создании шаблона проекта ATL или OLE DB для целевого объекта MinDependency установка и регистрация библиотеки ATL100.dll на целевом компьютере не требуются, но позволяют увеличить образ программы.  
  
 При распространении исполняемого приложения ATL необходимо зарегистрировать файл EXE (и все элементы управления внутри него), выполнив следующую команду:  
  
```  
filename /regserver  
```  
  
 где `filename` — это имя исполняемого файла.  
  
 Для приложений шаблонов OLE DB необходимо, чтобы на целевом компьютере были установлены последние версии файлов компонентов доступа к данным (MDAC). Дополнительные сведения см. в разделе [повторное распространение файлов поддержки базы данных](../ide/redistributing-database-support-files.md).  
  
## <a name="see-also"></a>См. также  
 [Распространение файлов Visual C++](../ide/redistributing-visual-cpp-files.md)