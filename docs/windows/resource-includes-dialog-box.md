---
title: Ресурс включает диалоговое окно (C++) | Документация Майкрософт
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
- Resource Includes dialog box [C++]
- rc files [C++], changing storage
- symbol header files [C++], changing
- .rc files [C++], changing storage
- symbol header files [C++], read-only
- symbols [C++], symbol header files
ms.assetid: 659a54e6-e416-4045-8411-798730ff4ce3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1263b5037d9e5ed3cf81eaa55f6e4accb8737e6b
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45705852"
---
# <a name="resource-includes-dialog-box-c"></a>Ресурс включает диалоговое окно (C++)

Можно использовать **включения ресурсов** диалогового окна в проекте C++, чтобы изменить обычную рабочую настройку среды хранение всех ресурсов в RC-файл проекта и все [символы](../windows/symbols-resource-identifiers.md) в файле Resource.h.

Чтобы открыть **включения ресурсов** диалоговое окно, щелкните правой кнопкой мыши RC файл в [представление ресурсов](../windows/resource-view-window.md), затем выберите **включения ресурсов** в контекстном меню.

- **Файл символов заголовков**

   Позволяет изменить имя файла заголовков, в котором хранятся определения символов файла ресурсов. Дополнительные сведения см. в разделе [изменение имен файлов символов заголовков](../windows/changing-the-names-of-symbol-header-files.md).

- **Директивы символов только для чтения**

   Позволяет включать файлы заголовков, содержащие символы, которые не должны изменяться во время сеанса редактирования. Например, можно включить файл символов, который является общим для нескольких проектов. Можно также включать H-файлы MFC. Дополнительные сведения см. в разделе [Включение общих (только для чтения) или вычисляемых символов](../windows/including-shared-read-only-or-calculated-symbols.md).

- **Директивы времени компиляции**

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