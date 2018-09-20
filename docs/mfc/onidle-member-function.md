---
title: Функция-член OnIdle | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- OnIdle
dev_langs:
- C++
helpviewer_keywords:
- processing messages [MFC]
- OnIdle method [MFC]
- idle loop processing [MFC]
- CWinApp class [MFC], OnIdle method [MFC]
- message handling [MFC], OnIdle method [MFC]
ms.assetid: 51adc874-0075-4f76-be1c-79283f46c10b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9b334a4561af40b69bc367ab5b1129afa8fb29ae
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46377303"
---
# <a name="onidle-member-function"></a>Функция-член OnIdle

При обработке сообщений Windows, платформа вызывает [CWinApp](../mfc/reference/cwinapp-class.md) функция-член [OnIdle](../mfc/reference/cwinapp-class.md#onidle) (см. в справочном руководстве библиотеки MFC).

Переопределить `OnIdle` для выполнения фоновых задач. Версия по умолчанию обновляет состояние объектов пользовательского интерфейса, таких как кнопки панели инструментов и выполняет очистку временные объекты, создаваемые платформой во время его операции. На следующем рисунке показано, как цикл обработки сообщений вызывает `OnIdle` при наличии в очереди нет сообщений.

![Процесс цикла сообщений](../mfc/media/vc387c1.gif "vc387c1") цикл обработки сообщений

Дополнительные сведения о возможностях в цикл простоя, см. в разделе [обработку цикла простоя](../mfc/idle-loop-processing.md).

## <a name="see-also"></a>См. также

[CWinApp: класс приложений](../mfc/cwinapp-the-application-class.md)
