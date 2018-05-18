---
title: Предопределенные символы Win32 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Win32 [C++], predefined symbols
- symbols, Win32 predefined
- Windows API [C++], predefined symbols
ms.assetid: 45c8e193-ee2a-4024-bfc2-34d1ec9c9239
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f1ce2ed589d27cd1c0065692a2254bf334f9aa1b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
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