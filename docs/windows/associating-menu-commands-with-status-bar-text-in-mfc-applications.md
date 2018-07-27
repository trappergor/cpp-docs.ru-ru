---
title: Сопоставление команды меню с текстом строки состояния в приложениях MFC | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- status bars, associating menu items
- menus, status bar text
ms.assetid: 757c0e02-bc97-493f-bccd-6cc6887ebc64
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 17326bdb8fe01c9ad329db0a6c7e8178fdbb25e7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33864246"
---
# <a name="associating-menu-commands-with-status-bar-text-in-mfc-applications"></a>Привязка команд меню к тексту строки состояния в приложениях MFC
Приложение может отображать описательный текст для каждой команды меню, которую может выбрать пользователь. Для этого необходимо назначить строку текста для каждой команды меню, используя свойство **Prompt** (Подсказка) в окне "Свойства". Если в [таблице строк](../windows/string-editor.md) имеется строка, идентификатор которой совпадает с идентификатором команды, приложение MFC автоматически отобразит этот строковый ресурс в строке состояния выполняющегося приложения в момент, когда пользователь наведет указатель мыши на пункт меню.  
  
### <a name="to-associate-a-menu-command-with-a-status-bar-text-string"></a>Чтобы связать команду меню со строкой текста в строке состояния, выполните следующие действия.  
  
1.  В редакторе **меню** выберите команду меню.  
  
2.  В [окне "Свойства"](/visualstudio/ide/reference/properties-window)в поле **Prompt** (Подсказка) введите нужный текст для строки состояния.  
  

  
 **Требования**  
  
 MFC  
  
## <a name="see-also"></a>См. также  
 [Строки (ATL и MFC)](../atl-mfc-shared/strings-atl-mfc.md)   
 [Добавление команд в меню](../windows/adding-commands-to-a-menu.md)   
 [Редактор меню](../windows/menu-editor.md)