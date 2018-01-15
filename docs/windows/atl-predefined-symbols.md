---
title: "Предопределенные символы ATL | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- symbols, ATL predefined
- ATL symbols
ms.assetid: 60d8f4e6-6ed9-47f3-9051-e4bf34384456
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d56fcfa8fb65f183acfe96c3981023d06f5e524a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="atl-predefined-symbols"></a>Предопределенные символы ATL
Эти символы определяются в файлах заголовков ATL, но они поддерживают стандартные функции приложения Windows и действия. Эти символы используются главным образом с диалоговыми окнами. При работе с диалоговых окон и элементов управления в [редактор диалоговых окон](../windows/dialog-editor.md), эти символы будут отображаться в окне свойств, связанных с типичными элементами управления. Например, если в диалоговом окне есть кнопка "Отмена", данная команда будет связана с символом IDCANCEL в [окно свойств](/visualstudio/ide/reference/properties-window).  
  
|||  
|-|-|  
|IDABORT|Элемента управления: Кнопку Abort поле диалогового окна|  
|IDC_STATIC|Элемент управления: Статический элемент управления|  
|IDCANCEL|Элемента управления: Кнопка отмены поле диалогового окна|  
|IDIGNORE|Элемента управления: Кнопка Пропустить поле диалогового окна|  
|IDNO|Элемент управления: Диалогового окна "," нет кнопки|  
|IDOK|Управления: Кнопка ОК поле диалогового окна|  
|IDR_ACCELERATOR1|Ресурсов: Таблицы сочетаний клавиш|  
|IDRETRY|Управления: Кнопку "Повторить" поле диалоговое окно|  
|IDS_PROJNAME|Строка: Имя текущего приложения|  
|IDYES|Управления: Диалоговое окно Да кнопку|  
  
## <a name="requirements"></a>Требования  
 ATL  
  
## <a name="see-also"></a>См. также  
 [Стандартные идентификаторы символов](../windows/predefined-symbol-ids.md)   
 [Символы: идентификаторы ресурсов](../windows/symbols-resource-identifiers.md)