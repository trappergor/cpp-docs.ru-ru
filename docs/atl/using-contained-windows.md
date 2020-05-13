---
title: Использование содержащихся Windows
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, windows
- windows [C++], ATL
- contained windows in ATL
ms.assetid: 7b3d79e5-b569-413f-9b98-df4f14efbe2b
ms.openlocfilehash: 5da765eae28d411c98e79af5b9173f48ea66ef8c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329306"
---
# <a name="using-contained-windows"></a>Использование содержащихся Windows

AtL орудия, содержащиеся окна с [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md). Содержащееся в нем окно представляет собой окно, которое делегирует свои сообщения объекту контейнера вместо обработки их в своем классе.

> [!NOTE]
> Вам не нужно получать класс `CContainedWindowT` из того, чтобы использовать содержащиеся окна.

С содержащимися окнами можно либо классифицировать существующий класс Windows, либо подклассировать существующее окно. Чтобы создать окно, которое классифицирует существующий класс Windows, сначала `CContainedWindowT` укажите существующее имя класса в конструкторе объекта. Затем `CContainedWindowT::Create`позвоните . Чтобы подклассировать существующее окно, не нужно указывать имя класса Windows (передайте NULL конструктору). Просто позвоните методу `CContainedWindowT::SubclassWindow` с подклассной ручкой к окну.

Обычно в качестве членов контейнерного класса используются содержащиеся окна. Контейнер не должен быть окном; однако, он должен быть получен из [CMessageMap](../atl/reference/cmessagemap-class.md).

В окне содержится альтернативные карты сообщений для обработки своих сообщений. Если у вас есть несколько содержащихся окна, вы должны объявить несколько альтернативных карт сообщений, каждая из которых соответствует отдельному содержащемуся окну.

## <a name="example"></a>Пример

Ниже приводится пример класса контейнеров с двумя содержащимися окнами:

[!code-cpp[NVC_ATL_Windowing#67](../atl/codesnippet/cpp/using-contained-windows_1.h)]

Для получения дополнительной информации о содержащихся окнах, [см.](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/Controls/SubEdit)

## <a name="see-also"></a>См. также раздел

[Классы окон](../atl/atl-window-classes.md)
