---
title: "Предопределенные символы Win32 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Win32 [C++], predefined symbols
- symbols, Win32 predefined
- Windows API [C++], predefined symbols
ms.assetid: 45c8e193-ee2a-4024-bfc2-34d1ec9c9239
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 01aa83fc5d0be468252b8593ee343ff28648d218
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="win32-predefined-symbols"></a>Предопределенные символы Win32
Эти символы определяются в файлах заголовков Win32, и они поддерживают стандартные функции приложения Windows и действия. Эти символы используются главным образом с помощью общих элементов пользовательского интерфейса. При работе с элементами управления ресурсами в редакторах, эти символы будут отображаться в [окно "Свойства"](/visualstudio/ide/reference/properties-window) связанного с типичными элементами управления. Например если на панель инструментов должна отображать значок приложения, значок будет связана с символом IDI_SMALL в окне свойств.  
  
|||  
|-|-|  
|IDABORT|Элемента управления: Кнопку Abort поле диалогового окна|  
|IDC_STATIC|Элемент управления: Статический текст в диалоговом окне|  
|IDCANCEL|Элемента управления: Кнопка отмены поле диалогового окна|  
|IDD_ABOUTBOX|Диалоговое окно: Продукта диалогового окна ""|  
|IDI_PROJECTNAME|Значок: Значок текущего проекта|  
|IDI_SMALL|Значок: Маленький значок текущего проекта|  
|IDIGNORE|Элемент управления: Используется с кнопка Пропустить о диалоговых окнах|  
|IDM_ABOUT|Пункт меню: Используется вместе с справки... О...|  
|IDM_EXIT|Пункт меню: Используется с файлом... Выход...|  
|IDNO|Элемент управления: Диалогового окна "," нет кнопки|  
|IDOK|Управления: Кнопка ОК поле диалогового окна|  
|IDRETRY|Управления: Кнопку "Повторить" поле диалоговое окно|  
|IDS_APP_TITLE|Строка: Имя текущего приложения|  
|IDYES|Управления: Диалоговое окно Да кнопку|  
  
## <a name="requirements"></a>Требования  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Стандартные идентификаторы символов](../windows/predefined-symbol-ids.md)   
 [Символы: идентификаторы ресурсов](../windows/symbols-resource-identifiers.md)