---
title: Страницы свойств средства создания XML-документов
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCXDCMakeTool.ValidateIntelliSense
- VC.Project.VCXDCMakeTool.SuppressStartupBanner
- VC.Project.VCXDCMakeTool.DocumentLibraryDependencies
- VC.Project.VCXDCMakeTool.OutputDocumentFile
- VC.Project.VCXDCMakeTool.AdditionalDocumentFiles
ms.assetid: 645912b5-197a-4c36-ba58-64df09444ca0
ms.openlocfilehash: c99677d7fc53ae3343e15e54997fe0101322fbcf
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57827503"
---
# <a name="xml-document-generator-tool-property-pages"></a>Страницы свойств средства создания XML-документов

Страница свойств для средства создания XML-документов предоставляет функциональные возможности xdcmake.exe. xdcmake.exe объединяет XDC-файлы с XML-файлами, если исходный код содержит комментарии документации и указан параметр [/doc (обработка комментариев в документации) (C/C++)](doc-process-documentation-comments-c-cpp.md). Сведения о добавлении комментариев документации в исходный код см. в разделе [Рекомендуемые теги для комментариев документации](recommended-tags-for-documentation-comments-visual-cpp.md).

> [!NOTE]
>  Параметры xdcmake.exe в среде разработки (страницы свойств) отличаются от параметров, доступных при использовании xdcmake.exe из командной строки. Сведения об использовании xdcmake.exe из командной строки см. в разделе [Справочник по XDCMake](xdcmake-reference.md).

## <a name="uielement-list"></a>Список элементов пользовательского интерфейса

- **Отключить загрузочное объявление**

   Позволяет запретить вывод сообщения об авторских правах.

- **Дополнительные файлы документации**

   Дополнительные каталоги, в которых система проектов должна искать XDC-файлы. Программа xdcmake всегда ищет XDC-файлы, созданные проектом. Можно указать несколько каталогов.

- **Выходной файл документации**

   Имя и каталог размещения для выходного XML-файла. См. в разделе [стандартные макросы для команд и свойств сборки](common-macros-for-build-commands-and-properties.md) сведения об использовании макросов для указания местоположения каталогов.

- **Зависимости библиотек документов**

   Если проект имеет зависимость от проекта LIB в решении, вы можете преобразовывать XDC-файлы из проекта LIB в XML-файлы для текущего проекта.

## <a name="see-also"></a>См. также

[Справочник по страницам свойств проекта C++](property-pages-visual-cpp.md)