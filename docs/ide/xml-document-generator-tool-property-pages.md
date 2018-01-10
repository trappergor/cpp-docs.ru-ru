---
title: "Страницы свойств средства создания документа XML | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCXDCMakeTool.ValidateIntelliSense
- VC.Project.VCXDCMakeTool.SuppressStartupBanner
- VC.Project.VCXDCMakeTool.DocumentLibraryDependencies
- VC.Project.VCXDCMakeTool.OutputDocumentFile
- VC.Project.VCXDCMakeTool.AdditionalDocumentFiles
dev_langs: C++
ms.assetid: 645912b5-197a-4c36-ba58-64df09444ca0
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bc09dafc0f07bc16a11dd255419440b6464456c5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="xml-document-generator-tool-property-pages"></a>Страницы свойств средства создания XML-документов
Страница свойств средство создания XML-документов предоставляет функциональные возможности xdcmake.exe. xdcmake.exe объединяет XDC-файлы в XML-файл, если исходный код содержит комментарии к документации и [/doc (обработка комментариев документации) (C/C++)](../build/reference/doc-process-documentation-comments-c-cpp.md) указано,. В разделе [Рекомендуемые теги для комментариев документации](../ide/recommended-tags-for-documentation-comments-visual-cpp.md) сведения о добавлении комментариев документации к исходному коду.  
  
> [!NOTE]
>  Параметры xdcmake.exe в среде разработки (страницы свойств) отличаются от параметров, доступных при использовании xdcmake.exe из командной строки. Сведения об использовании xdcmake.exe из командной строки см. в разделе [Справочник по XDCMake](../ide/xdcmake-reference.md).  
  
## <a name="uielement-list"></a>Список элементов пользовательского интерфейса  
 **Отключить загрузочное объявление**  
 Подавлять сообщения об авторских правах.  
  
 **Дополнительные файлы документации**  
 Дополнительные каталоги, в которых требуется систему проектов, чтобы искать XDC-файлы. Программа xdcmake всегда будет искать XDC-файлы, созданные в проект. Можно указать несколько каталогов.  
  
 **Выходной файл документации**  
 Имя и каталог размещения выходного XML-файла. В разделе [общие макросы для команд и свойств построения](../ide/common-macros-for-build-commands-and-properties.md) сведения об использовании макросов для указания расположения каталога.  
  
 **Зависимости библиотек документов**  
 Если проект имеет зависимость от проекта .lib в решении, может обрабатывать XDC-файлы проекта .lib в XML-файлы для текущего проекта.  
  
## <a name="see-also"></a>См. также  
 [Страницы свойств](../ide/property-pages-visual-cpp.md)   
 [Страницы свойств](../ide/property-pages-visual-cpp.md)