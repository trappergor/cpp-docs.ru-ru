---
title: "Справочник по XDCMake | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "xdcmake"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "программа xdcmake"
ms.assetid: 14e65747-d000-4343-854b-8393bf01cbac
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# Справочник по XDCMake
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

xdcmake.exe программы, компилировать файлы .xdc в XML\-файл.  Файл .xdc создается компилятором Visual C\+\+ C для каждого файла исходного кода, когда исходный код компилироваться с [\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) и когда файл исходного кода комментариями документации, помеченные тегами вверх с XML.  
  
### Использовать xdcmake.exe среды разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Открытие свойств страниц проекта](../misc/how-to-open-project-property-pages.md).  
  
2.  Откройте папку **Свойства конфигурации**.  
  
3.  Щелкните страницу свойств **Документирующие комментарии XML**.  
  
> [!NOTE]
>  параметры xdcmake.exe в командной строке отличаются от параметров при xdcmake.exe используется среды разработки \(страниц свойств\).  Дополнительные сведения об использовании xdcmake.exe среды разработки см. в разделе [Страницы свойств средства создания XML\-документов](../Topic/XML%20Document%20Generator%20Tool%20Property%20Pages.md).  
  
## Синтаксис  
 xdcmake `input_filename options`  
  
## Параметры  
 Здесь:  
  
 `input_filename`  
 Имя файлов .xdc, используемых в качестве входных данных для xdcmake.exe.  Укажите один или несколько файлов .xdc или используйте \*.xdc использование всех файлов .xdc в текущем каталоге.  
  
 `options`  
 Одно или несколько из следующих действий:  
  
|Параметр|Описание|  
|--------------|--------------|  
|\/? \- \/help|Отображение справки для xdcmake.exe.|  
|\/assembly:*имя файла*|Позволяет задать значение тега \<assembly\> XML\-файла.  По умолчанию значение тега \<assembly\> совпадает с именем файла XML.|  
|\/nologo|Уведомление об авторских правах не выводится.|  
|\/out:*имя файла*|Позволяет задать имя файла XML.  По умолчанию имя файла XML имя файла первого файла .xdc обрабатываемого xdcmake.exe.|  
  
## Заметки  
 Visual Studio будет xdcmake.exe автоматически при построении проекта.  Можно также вызвать xdcmake.exe в командной строке.  
  
 Дополнительные сведения см. в разделе [Рекомендуемые теги для комментариев документации](../Topic/Recommended%20Tags%20for%20Documentation%20Comments%20\(Visual%20C++\).md) на добавление документирующие комментарии к файлам исходного кода.  
  
## См. также  
 [Документация XML](../ide/xml-documentation-visual-cpp.md)