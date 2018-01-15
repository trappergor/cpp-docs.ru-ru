---
title: "Стандартные идентификаторы символов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- symbols, predefined IDs
- predefined symbol IDs
ms.assetid: 91a5d610-1a04-47e8-b8a4-63ad650a90df
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e431ce20361a9a7d3d05676d1b9da01b98c07d5a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="predefined-symbol-ids"></a>Стандартные идентификаторы символов
В начале работы над новым проектом в зависимости от типа проекта предоставляется ряд предопределенных идентификаторов символов, которые можно использовать. Эти идентификаторы символов поддерживают различные библиотеки и типы проектов, например MFC. Они представляют типичные задачи, которые обычно включаются в любое приложение, или действия таких устройств, как мышь или принтер.  
  
 Эти идентификаторы символов становятся важными при работе с ресурсами. Они доступны при редактировании таблиц сочетаний клавиш. Некоторые из них уже связаны с виртуальными клавишами. Также доступны при использовании [окно свойств](/visualstudio/ide/reference/properties-window). Предопределенные идентификаторы символов можно назначать новым ресурсам, или можно назначать им сочетания клавиш и функции, связанные с идентификаторами символов, будут автоматически связаны с этими сочетаниями клавиш.  
  
 Эти библиотеки содержат предопределенные символы, которые будут отображаться как составная часть проекта:  
  
-   [Предопределенные символы MFC](../windows/mfc-predefined-symbols.md)  
  
-   [Предопределенные символы ATL](../windows/atl-predefined-symbols.md)  
  
-   [Предопределенные символы Win32](../windows/win32-predefined-symbols.md)  
  
    > [!NOTE]
    >  Предопределенные символы всегда доступны только для чтения.  
  

  
## <a name="requirements"></a>Требования  
 Win32, MFC или ATL  
  
## <a name="see-also"></a>См. также  
 [Символы: идентификаторы ресурсов](../windows/symbols-resource-identifiers.md)