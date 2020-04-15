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
ms.openlocfilehash: d17913909532c5bebcac712937af00be3ad98712
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335770"
---
# <a name="xml-document-generator-tool-property-pages"></a>Страницы свойств средства создания XML-документов

Страница свойств для средства создания XML-документов предоставляет функциональные возможности xdcmake.exe. xdcmake.exe объединяет XDC-файлы с XML-файлами, если исходный код содержит комментарии документации и указан параметр [/doc (обработка комментариев в документации) (C/C++)](doc-process-documentation-comments-c-cpp.md). Сведения о добавлении комментариев документации в исходный код см. в разделе [Рекомендуемые теги для комментариев документации](recommended-tags-for-documentation-comments-visual-cpp.md).

> [!NOTE]
> Параметры xdcmake.exe в среде разработки (страницы свойств) отличаются от параметров, доступных при использовании xdcmake.exe из командной строки. Сведения об использовании xdcmake.exe из командной строки см. в разделе [Справочник по XDCMake](xdcmake-reference.md).

## <a name="uielement-list"></a>Список элементов пользовательского интерфейса

- **Отключить загрузочный баннер**

   Позволяет запретить вывод сообщения об авторских правах.

- **Дополнительные файлы документации**

   Дополнительные каталоги, в которых система проектов должна искать XDC-файлы. Программа xdcmake всегда ищет XDC-файлы, созданные проектом. Можно указать несколько каталогов.

- **Выходной файл документации**

   Имя и каталог размещения для выходного XML-файла. См [Общие макросы для создания команд и свойств](common-macros-for-build-commands-and-properties.md) для получения информации об использовании макросов для указания местоположений каталогов.

- **Зависимости библиотек документов**

   Если проект имеет зависимость от проекта LIB в решении, вы можете преобразовывать XDC-файлы из проекта LIB в XML-файлы для текущего проекта.

## <a name="see-also"></a>См. также раздел

[Ссылка на свойство проекта «СИ»](property-pages-visual-cpp.md)
