---
title: Добавление функциональных возможностей в составной элемент управления | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- event handlers [C++], ActiveX controls
- composite controls, handling events
- ActiveX controls [C++], events
ms.assetid: 98f85681-9564-480d-af38-03f9733fe58b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 59ee8047e17efdebbae6ee58ec243057a477caff
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43751137"
---
# <a name="adding-functionality-to-the-composite-control"></a>Добавление функциональных возможностей в составной элемент управления

После добавления всех необходимых элементов управления в составной элемент управления, следующим этапом является добавление новых функциональных возможностей. Эти новые функции обычно разделяется на две категории:

- Поддержка дополнительных интерфейсов и настройки поведения элемента управления с помощью дополнительной функции.

- Обработка событий из содержащегося элемента управления ActiveX (или элементов управления).

Для цели и рамки этой статьи в оставшейся части этого раздела посвящена исключительно обработка событий элементов управления ActiveX.

> [!NOTE]
>  Если вам нужно обрабатывать сообщения от элементов управления Windows, см. в разделе [реализация окна](../atl/implementing-a-window.md) узнать больше о обработки сообщений в ATL.

После вставки элемента управления ActiveX в ресурс диалогового окна, щелкните правой кнопкой мыши элемент управления и нажмите кнопку **добавить обработчик событий**. Выберите событие, для обработки и нажмите кнопку **добавлять и редактировать**. Код обработчика событий будет добавляться h-файл элемента управления.

Точки подключения для элементов управления ActiveX в составной элемент управления автоматически подключены и через вызовы к отключении [CComCompositeControl::AdviseSinkMap](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap).

## <a name="see-also"></a>См. также

[Основы составного элемента управления](../atl/atl-composite-control-fundamentals.md)

