---
title: Диалоговое окно включения ресурсов | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.resourceincludes
dev_langs:
- C++
helpviewer_keywords:
- Resource Includes dialog box
- rc files, changing storage
- symbol header files, changing
- compiling source code, including resources
- .rc files, changing storage
- symbol header files, read-only
- symbols, symbol header files
ms.assetid: 659a54e6-e416-4045-8411-798730ff4ce3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 96ee92f1b21d67321b95a169cbc4c47eaca2de17
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42610665"
---
# <a name="resource-includes-dialog-box"></a>включения ресурсов - Диалоговое окно

Можно использовать **включения ресурсов** диалоговое окно, чтобы изменить обычную рабочую настройку среды хранение всех ресурсов в RC-файл проекта и все [символы](../windows/symbols-resource-identifiers.md) в файле Resource.h.

Чтобы открыть **включения ресурсов** диалоговое окно, щелкните правой кнопкой мыши RC файл в [представление ресурсов](../windows/resource-view-window.md), затем выберите **включения ресурсов** в контекстном меню.

**Файл символов заголовков**  
Позволяет изменить имя файла заголовков, в котором хранятся определения символов файла ресурсов. Дополнительные сведения см. в разделе [изменение имен файлов символов заголовков](../windows/changing-the-names-of-symbol-header-files.md).

**Директивы символов только для чтения**  
Позволяет включать файлы заголовков, содержащие символы, которые не должны изменяться во время сеанса редактирования. Например, можно включить файл символов, который является общим для нескольких проектов. Можно также включать H-файлы MFC. Дополнительные сведения см. в разделе [Включение общих (только для чтения) или вычисляемых символов](../windows/including-shared-read-only-or-calculated-symbols.md).

**Директивы времени компиляции**  
Позволяет включать файлы ресурсов, созданные и отредактированные отдельно от ресурсов основного файла, включать директивы времени компиляции (например, такие, которые условно включают ресурсы) или ресурсы в нестандартном формате. Можно также использовать **поле директив времени компиляции** для включения стандартных файлов ресурсов MFC. Дополнительные сведения см. в разделе [Включение ресурсов во время компиляции](../windows/how-to-include-resources-at-compile-time.md).

> [!NOTE]
> Записи в этих полях появляются в RC-файл, отмеченный `TEXTINCLUDE 1`, `TEXTINCLUDE 2`, и `TEXTINCLUDE 3` соответственно. Дополнительные сведения см. в разделе [TN035: использование нескольких файлов ресурсов и файлов заголовков в Visual C++](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md).

После внесения изменений в файл ресурсов с помощью **включения ресурсов** диалоговое окно, необходимо закрыть RC-файл и снова откройте его, чтобы изменения вступили в силу. Дополнительные сведения см. в разделе [Включение ресурсов во время компиляции](../windows/how-to-include-resources-at-compile-time.md).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Практическое руководство. Указание каталогов включения для ресурсов](../windows/how-to-specify-include-directories-for-resources.md)  
[Символы: идентификаторы ресурсов](../windows/symbols-resource-identifiers.md)  
[Файлы ресурсов](../windows/resource-files-visual-studio.md)  
[Редакторы ресурсов](../windows/resource-editors.md)