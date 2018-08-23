---
title: Предопределенные символы ATL | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- symbols, ATL predefined
- ATL symbols
ms.assetid: 60d8f4e6-6ed9-47f3-9051-e4bf34384456
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0f504573de959286cc2fadb5c42c2a216c5073de
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42600574"
---
# <a name="atl-predefined-symbols"></a>Предопределенные символы ATL

Эти символы определяются в файлах заголовков ATL, но они поддерживают стандартные функции приложения Windows и действия. Эти символы используются главным образом с диалоговыми окнами. При работе с элементами управления и диалоговых окон в [редактор диалоговых окон](../windows/dialog-editor.md), эти символы будут отображаться в **свойства** окно, связанное с помощью стандартных элементов управления. Например если в диалоговом окне есть **отменить** кнопку, что команда будет связана с символом IDCANCEL в [окно "Свойства"](/visualstudio/ide/reference/properties-window).

|||
|-|-|
|IDABORT|Управления: Кнопка прерывания полю диалоговое окно|
|IDC_STATIC|Элемента управления: Статический элемент управления|
|IDCANCEL|Элемент управления: Кнопки диалогового окна "Отмена"|
|IDIGNORE|Элемента управления: Кнопка Пропустить поле диалогового окна|
|IDNO|Элемент управления: Диалоговое окно кнопка "Нет"|
|IDOK|Управления: Кнопки ОК поле диалогового окна|
|IDR_ACCELERATOR1|Ресурсов: Таблицы сочетаний клавиш|
|IDRETRY|Элемента управления: Кнопка повтора поле диалогового окна|
|IDS_PROJNAME|Строка: Имя текущего приложения|
|IDYES|Управления: Диалоговое окно Да кнопку|

## <a name="requirements"></a>Требования

ATL

## <a name="see-also"></a>См. также

[Стандартные идентификаторы символов](../windows/predefined-symbol-ids.md)  
[Символы: идентификаторы ресурсов](../windows/symbols-resource-identifiers.md)