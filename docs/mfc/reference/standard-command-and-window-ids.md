---
title: "Стандартная команда и идентификаторы окон | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- standard command and Window IDs
ms.assetid: 0424805c-fff8-4531-8f0c-15cfb13aa612
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2c8195b1ab967a0d6692e839b1db1e89ee6694d5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="standard-command-and-window-ids"></a>Стандартная команда и идентификаторы окон
Библиотеки классов Microsoft Foundation определяет количество стандартная команда и идентификаторы окон в файле Afxres.h. Эти идентификаторы наиболее часто используются в редакторы ресурсов и окне «Свойства» для сопоставления сообщения с функций-обработчиков. Все стандартные команды имеют **ID_** префикс. Например, при использовании редактора меню обычно привязке элемента меню открытия файла стандарта `ID_FILE_OPEN` команды идентификатор.  
  
 Большинство стандартных команд кода приложения не требуется для ссылки на идентификатор команды, так как сама инфраструктура обрабатывает команды через схемы сообщений в его основной framework классов ( `CWinThread`, `CWinApp`, < c4 Настроек `CView` , **CDocument**и так далее).  
  
 Помимо стандартных идентификаторов команд, определенных ряд других стандартных кодов которого имеют префикс из **AFX_ID**. Эти идентификаторы включают стандартное окно идентификаторы (префикс **AFX_IDW_**), строка, идентификаторы (префикс **AFX_IDS_**) и несколько других типов.  
  
 Идентификаторы, начинающиеся с **AFX_ID** префикс редко используются разработчиками, однако может потребоваться для ссылки на эти идентификаторы при переопределении функции framework, которые также ссылаются на **AFX_ID**s.  
  
 Идентификаторы не документированы в этом справочнике по отдельности. Дополнительные сведения о них можно найти в Технические примечания [20](../../mfc/tn020-id-naming-and-numbering-conventions.md), [21](../../mfc/tn021-command-and-message-routing.md), и [22](../../mfc/tn022-standard-commands-implementation.md).  
  
> [!NOTE]
>  Файл заголовка Afxres.h неявно включается в Afxwin.h. Явным образом, необходимо включить следующую инструкцию в RC-файл приложения ресурсов:  
  
 [!code-cpp[NVC_MFC_Utilities#47](../../mfc/codesnippet/cpp/standard-command-and-window-ids_1.h)]  
  
## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
