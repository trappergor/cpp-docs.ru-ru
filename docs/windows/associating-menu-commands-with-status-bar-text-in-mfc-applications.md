---
title: Привязка команд меню к тексту строки состояния в приложениях MFC | Документация Майкрософт
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
ms.openlocfilehash: d9cb5e57d6c7020e0b89104dac87fa3cd08ea023
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42583705"
---
# <a name="associating-menu-commands-with-status-bar-text-in-mfc-applications"></a>Привязка команд меню к тексту строки состояния в приложениях MFC

Приложение может отображать описательный текст для каждой команды меню, которую может выбрать пользователь. Добиться этого можно назначить строку текста для каждой команды меню, используя **Prompt** свойство в **свойства** окна. Если в [таблице строк](../windows/string-editor.md) имеется строка, идентификатор которой совпадает с идентификатором команды, приложение MFC автоматически отобразит этот строковый ресурс в строке состояния выполняющегося приложения в момент, когда пользователь наведет указатель мыши на пункт меню.

### <a name="to-associate-a-menu-command-with-a-status-bar-text-string"></a>Чтобы связать команду меню со строкой текста в строке состояния, выполните следующие действия.

1. В редакторе **меню** выберите команду меню.

2. В [окне "Свойства"](/visualstudio/ide/reference/properties-window)в поле **Prompt** (Подсказка) введите нужный текст для строки состояния.

## <a name="requirements"></a>Требования

MFC

## <a name="see-also"></a>См. также

[Строки (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)  
[Добавление команд в меню](../windows/adding-commands-to-a-menu.md)  
[Редактор меню](../windows/menu-editor.md)