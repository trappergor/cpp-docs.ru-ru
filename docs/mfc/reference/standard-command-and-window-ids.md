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
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: d308f3f9efc5933124460d9839a0e94fffa60b4a
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="standard-command-and-window-ids"></a>Стандартная команда и идентификаторы окон
Библиотеки классов Microsoft Foundation определяет количество стандартная команда и идентификаторы окон в файле Afxres.h. Эти идентификаторы наиболее часто используются в редакторы ресурсов и в окне «Свойства» для сопоставления функций-обработчиков сообщений. Все стандартные команды имеют **ID_** префикс. Например, при использовании редактора меню обычно привязке элемента меню File Open стандарта `ID_FILE_OPEN` команды идентификатор.  
  
 Для большинство стандартных команд, код приложения не требуется для ссылки на идентификатор команды, поскольку сама инфраструктура обрабатывает команды по схемам сообщений в классах основной framework ( `CWinThread`, `CWinApp`, `CView`, **CDocument**и так далее).  
  
 Помимо стандартных идентификаторов команд, ряд других стандартных идентификаторов определяются которого имеют префикс из **AFX_ID**. Эти идентификаторы включают стандартное окно идентификаторы (префикс **AFX_IDW_**), строка, идентификаторы (префикс **AFX_IDS_**) и несколько других типов.  
  
 Идентификаторы, начинающиеся с **AFX_ID** префикс редко используются разработчиками, но может понадобиться для ссылки на эти идентификаторы при переопределении функции framework, которые также называют **AFX_ID**s.  
  
 Идентификаторы не документированы в этом справочнике по отдельности. Дополнительные сведения о них можно найти в Технические примечания [20](../../mfc/tn020-id-naming-and-numbering-conventions.md), [21](../../mfc/tn021-command-and-message-routing.md), и [22](../../mfc/tn022-standard-commands-implementation.md).  
  
> [!NOTE]
>  Файл заголовка Afxres.h неявно включается в Afxwin.h. Явным образом, необходимо включить следующую инструкцию в RC-файл приложения ресурсов:  
  
 [!code-cpp[NVC_MFC_Utilities&#47;](../../mfc/codesnippet/cpp/standard-command-and-window-ids_1.h)]  
  
## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)

