---
title: "Диалоговое окно включения ресурсов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.editors.resourceincludes
dev_langs: C++
helpviewer_keywords:
- Resource Includes dialog box
- rc files, changing storage
- symbol header files, changing
- compiling source code, including resources
- .rc files, changing storage
- symbol header files, read-only
- symbols, symbol header files
ms.assetid: 659a54e6-e416-4045-8411-798730ff4ce3
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 610e970ad84c6c89d91182b7a61bb759112fcd7d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="resource-includes-dialog-box"></a>включения ресурсов - Диалоговое окно
Можно использовать **включения ресурсов** диалогового окна для изменения среды в обычное рабочее расположение хранение всех ресурсов в RC-файл проекта и все [символы](../windows/symbols-resource-identifiers.md) в файле Resource.h.  
  
 Чтобы открыть **включения ресурсов** диалоговое окно, щелкните правой кнопкой мыши RC файла в [представление ресурсов](../windows/resource-view-window.md), выберите **включения ресурсов** в контекстном меню.  
  
 **Файл символов заголовка**  
 Позволяет изменить имя файла заголовков, в котором хранятся определения символов файла ресурсов. Дополнительные сведения см. в разделе [изменение имен файлов символов заголовков](../windows/changing-the-names-of-symbol-header-files.md).  
  
 **Директивы символов только для чтения**  
 Позволяет включать файлы заголовков, содержащие символы, которые не должны изменяться во время сеанса редактирования. Например, можно включить файл символов, который является общим для нескольких проектов. Можно также включать H-файлы MFC. Дополнительные сведения см. в разделе [Включение общих (только для чтения) или вычисляемых символов](../windows/including-shared-read-only-or-calculated-symbols.md).  
  
 **Директивы времени компиляции**  
 Позволяет включать файлы ресурсов, созданные и отредактированные отдельно от ресурсов основного файла, включать директивы времени компиляции (например, такие, которые условно включают ресурсы) или ресурсы в нестандартном формате. Поле директив времени компиляции можно также использовать для включения стандартных файлов ресурсов MFC. Дополнительные сведения см. в разделе [Включение ресурсов во время компиляции](../windows/how-to-include-resources-at-compile-time.md).  
  
> [!NOTE]
>  Элементы в этих полях отображаются в RC-файл, помеченный `TEXTINCLUDE 1`, `TEXTINCLUDE 2`, и `TEXTINCLUDE 3` соответственно. Дополнительные сведения см. в разделе [TN035: использование нескольких файлов ресурсов и файлов заголовков в Visual C++](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md).  
  
 После внесения изменений в файл ресурсов с помощью **включения ресурсов** диалоговое окно, необходимо закрыть RC-файл и снова откройте его, чтобы изменения вступили в силу. Дополнительные сведения см. в разделе [Включение ресурсов во время компиляции](../windows/how-to-include-resources-at-compile-time.md).  
  

  
## <a name="requirements"></a>Требования  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Как: укажите каталогов включения для ресурсов](../windows/how-to-specify-include-directories-for-resources.md)   
 [Символы: Идентификаторы ресурсов](../windows/symbols-resource-identifiers.md)   
 [Файлы ресурсов](../windows/resource-files-visual-studio.md)   
 [Редакторы ресурсов](../windows/resource-editors.md)