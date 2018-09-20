---
title: Асинхронные моникеры в Интернете | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [MFC], asynchronous
- MFC, asynchronous monikers
- asynchronous monikers [MFC]
- Web applications [MFC], asynchronous
- downloading Internet resources and asynchronous monikers
- optimization [MFC], asynchronous downloading across Internet
- Internet [MFC], asynchronous downloading
ms.assetid: 418b0c64-0046-4dae-8118-c9c762b5822e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bdb310891cd98e6bf3a8afa0b92cce01e5f5c6ba
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46409909"
---
# <a name="asynchronous-monikers-on-the-internet"></a>Асинхронные моникеры в Интернете

Интернет требуются новые подходы к разработке приложения из-за его доступ к медленной сети. Приложения должны выполнять доступ к сети асинхронно, чтобы избежать замедляющих работу пользовательского интерфейса. Класс MFC [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md) предоставляет поддержку асинхронных операций для загрузки файлов.

С помощью асинхронных моникеров вы можете расширить COM-приложения для загрузки асинхронно через Интернет и обеспечивают Прогрессивная отрисовка больших объектов, таких как точечные рисунки и VRML объектов. Асинхронные моникеры включить свойство элемента управления ActiveX или файл в Интернете, чтобы загрузить без блокировки отклика пользовательского интерфейса.

## <a name="advantages-of-asynchronous-monikers"></a>Преимущества использования асинхронных моникеров

Можно использовать асинхронные моникеры для:

- Загрузите код и файлы без блокировки.

- Загрузка свойств элементов управления ActiveX без блокировки.

- Получайте уведомления о ходе выполнения загрузки.

- Отслеживание хода выполнения и сведения о состоянии "Готово".

- Предоставить сведения о состоянии пользователю о ходе выполнения.

- Разрешить пользователю отменить загрузку в любое время.

## <a name="mfc-classes-for-asynchronous-monikers"></a>Классы MFC для асинхронных моникеров

[CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md) является производным от [CMonikerFile](../mfc/reference/cmonikerfile-class.md), который в свою очередь является производным от [COleStreamFile](../mfc/reference/colestreamfile-class.md). Объект `COleStreamFile` объект представляет поток данных; `CMonikerFile` объектов используют `IMoniker` для получения данных и `CAsyncMonikerFile` объект делает это асинхронно.

Асинхронные моникеры используются главным образом в Интернет-приложений и элементов управления ActiveX для обеспечения создания быстродействующего пользовательского интерфейса во время передачи файлов. Хорошим примером этого является использование [CDataPathProperty](../mfc/reference/cdatapathproperty-class.md) для предоставления асинхронного свойств для элементов управления ActiveX.

## <a name="mfc-classes-for-data-paths-in-activex-controls"></a>Классы MFC для пути к данным в элементах управления ActiveX

Классы MFC `CDataPathProperty` и [CCachedDataPathProperty](../mfc/reference/ccacheddatapathproperty-class.md) реализовать свойства элемента управления ActiveX, которые могут быть загружены асинхронно. Асинхронные свойства загружаются после синхронного запуска. Асинхронные элементы управления ActiveX многократном запуске обратный вызов для указания доступности новых данных во время длительных свойство exchange.

Класс `CDataPathProperty` является производным от `CAsyncMonikerFile`. Класс `CCachedDataPathProperty` является производным от `CDataPathProperty`. Для реализации асинхронных свойств в элементах управления ActiveX, наследуйте класс от `CDataPathProperty` или `CCachedDataPathProperty`и Переопределите [OnDataAvailable](../mfc/reference/casyncmonikerfile-class.md#ondataavailable) и других уведомлений, вы хотите получать.

#### <a name="to-download-a-file-using-asynchronous-monikers"></a>Чтобы загрузить файл, используя асинхронные моникеры

1. Объявите класс, производный от [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md).

1. Переопределить [OnDataAvailable](../mfc/reference/casyncmonikerfile-class.md#ondataavailable) для отображения данных.

1. Переопределить другие функции-члены, включая [OnProgress](../mfc/reference/casyncmonikerfile-class.md#onprogress), [OnStartBinding](../mfc/reference/casyncmonikerfile-class.md#onstartbinding), и [OnStopBinding](../mfc/reference/casyncmonikerfile-class.md#onstopbinding).

1. Объявите экземпляр этого класса и использовать его для открытия URL-адресов.

Сведения о загрузке асинхронно в элементе управления ActiveX, см. в разделе [элементы управления ActiveX в Интернете](../mfc/activex-controls-on-the-internet.md).

## <a name="see-also"></a>См. также

[Задачи программирования для интернет-решений MFC](../mfc/mfc-internet-programming-tasks.md)<br/>
[Основы программирования для интернет-решений MFC](../mfc/mfc-internet-programming-basics.md)

