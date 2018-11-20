---
title: Функция-член OnIdle
ms.date: 11/19/2018
f1_keywords:
- OnIdle
helpviewer_keywords:
- processing messages [MFC]
- OnIdle method [MFC]
- idle loop processing [MFC]
- CWinApp class [MFC], OnIdle method [MFC]
- message handling [MFC], OnIdle method [MFC]
ms.assetid: 51adc874-0075-4f76-be1c-79283f46c10b
ms.openlocfilehash: 7b3f2fbeac6ae356003abf12b5df4c54c8bb327a
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2018
ms.locfileid: "52175137"
---
# <a name="onidle-member-function"></a>Функция-член OnIdle

При обработке сообщений Windows, платформа вызывает [CWinApp](../mfc/reference/cwinapp-class.md) функция-член [OnIdle](../mfc/reference/cwinapp-class.md#onidle) (см. в справочном руководстве библиотеки MFC).

Переопределить `OnIdle` для выполнения фоновых задач. Версия по умолчанию обновляет состояние объектов пользовательского интерфейса, таких как кнопки панели инструментов и выполняет очистку временные объекты, создаваемые платформой во время его операции. На следующем рисунке показано, как цикл обработки сообщений вызывает `OnIdle` при наличии в очереди нет сообщений.

![Процесс цикла сообщений](../mfc/media/vc387c1.gif "процесс цикла сообщений") <br/>
Цикл обработки сообщений

Дополнительные сведения о возможностях в цикл простоя, см. в разделе [обработку цикла простоя](../mfc/idle-loop-processing.md).

## <a name="see-also"></a>См. также

[CWinApp: класс приложений](../mfc/cwinapp-the-application-class.md)
