---
title: Страницы свойств для средства создания XML-документов | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCXDCMakeTool.ValidateIntelliSense
- VC.Project.VCXDCMakeTool.SuppressStartupBanner
- VC.Project.VCXDCMakeTool.DocumentLibraryDependencies
- VC.Project.VCXDCMakeTool.OutputDocumentFile
- VC.Project.VCXDCMakeTool.AdditionalDocumentFiles
dev_langs:
- C++
ms.assetid: 645912b5-197a-4c36-ba58-64df09444ca0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1ee18e32d1aaf2a9035b425cb3c3ef5e2db15145
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45718813"
---
# <a name="xml-document-generator-tool-property-pages"></a>Страницы свойств средства создания XML-документов
Страница свойств для средства создания XML-документов предоставляет функциональные возможности xdcmake.exe. xdcmake.exe объединяет XDC-файлы с XML-файлами, если исходный код содержит комментарии документации и указан параметр [/doc (обработка комментариев в документации) (C/C++)](../build/reference/doc-process-documentation-comments-c-cpp.md). Сведения о добавлении комментариев документации в исходный код см. в разделе [Рекомендуемые теги для комментариев документации](../ide/recommended-tags-for-documentation-comments-visual-cpp.md).  
  
> [!NOTE]
>  Параметры xdcmake.exe в среде разработки (страницы свойств) отличаются от параметров, доступных при использовании xdcmake.exe из командной строки. Сведения об использовании xdcmake.exe из командной строки см. в разделе [Справочник по XDCMake](../ide/xdcmake-reference.md).  
  
## <a name="uielement-list"></a>Список элементов пользовательского интерфейса  
- **Отключить загрузочное объявление**

   Позволяет запретить вывод сообщения об авторских правах.  
  
- **Дополнительные файлы документации**

   Дополнительные каталоги, в которых система проектов должна искать XDC-файлы. Программа xdcmake всегда ищет XDC-файлы, созданные проектом. Можно указать несколько каталогов.  
  
- **Выходной файл документации**

   Имя и каталог размещения для выходного XML-файла. Сведения об использовании макросов для указания каталогов см. в разделе [Стандартные макросы для команд и свойств сборки](../ide/common-macros-for-build-commands-and-properties.md).  
  
- **Зависимости библиотек документов**

   Если проект имеет зависимость от проекта LIB в решении, вы можете преобразовывать XDC-файлы из проекта LIB в XML-файлы для текущего проекта.  
  
## <a name="see-also"></a>См. также  
 [Страницы свойств](../ide/property-pages-visual-cpp.md)   
 [Страницы свойств](../ide/property-pages-visual-cpp.md)