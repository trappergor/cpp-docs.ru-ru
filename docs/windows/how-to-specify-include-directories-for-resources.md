---
title: 'Практическое: укажите каталогов включения для ресурсов | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- directories [C++], specifying include paths for resources
- include files, specifying for resources
- resources [Visual Studio], including in projects
ms.assetid: d6a7c0f6-4810-4bb0-b4b7-7d2476a20ca2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: baa317610339e7073f2e829860e11ab15e66277e
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42611065"
---
# <a name="how-to-specify-include-directories-for-resources"></a>Практическое руководство. Указание каталогов включения для ресурсов

### <a name="to-specify-include-directories-for-a-specific-rc-file"></a>Для указания включите каталоги для конкретного rc-файла

1. Щелкните правой кнопкой мыши RC-файл в обозревателе решений и выберите **свойства** в контекстном меню.

2. В **страницы свойств** диалоговом окне щелкните **ресурсы** узел в области слева, затем укажите дополнительные каталоги включения в **Дополнительные каталоги включаемых файлов** свойство.

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) руководства разработчика .NET Framework. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Пошаговое руководство: Using Resources for Localization with ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Диалоговое окно "Включения ресурсов"](../windows/resource-includes-dialog-box.md)  
[TN035. Использование нескольких файлов ресурсов и файлов заголовков в Visual C++](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md)  
[Символы: идентификаторы ресурсов](../windows/symbols-resource-identifiers.md)  
[Файлы ресурсов](../windows/resource-files-visual-studio.md)  
[Редакторы ресурсов](../windows/resource-editors.md)