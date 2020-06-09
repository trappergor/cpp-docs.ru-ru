---
title: Асинхронные моникеры в Интернете
ms.date: 11/04/2016
helpviewer_keywords:
- ActiveX controls [MFC], asynchronous
- MFC, asynchronous monikers
- asynchronous monikers [MFC]
- Web applications [MFC], asynchronous
- downloading Internet resources and asynchronous monikers
- optimization [MFC], asynchronous downloading across Internet
- Internet [MFC], asynchronous downloading
ms.assetid: 418b0c64-0046-4dae-8118-c9c762b5822e
ms.openlocfilehash: 74add1ad894f883c67eefab888898c0abf518b83
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84625031"
---
# <a name="asynchronous-monikers-on-the-internet"></a>Асинхронные моникеры в Интернете

Интернет требует новых подходов к проектированию приложений из-за высокой скорости доступа к сети. Приложения должны выполнять асинхронный доступ к сети, чтобы предотвратить зависание пользовательского интерфейса. Класс MFC [касинкмоникерфиле](reference/casyncmonikerfile-class.md) обеспечивает асинхронную поддержку загрузки файлов.

С помощью асинхронных моникеров можно расширить приложение COM для асинхронного скачивания через Интернет и обеспечить последовательную отрисовку больших объектов, таких как точечные рисунки и объекты ВРМЛ. Асинхронные моникеры позволяют загрузить свойство элемента управления ActiveX или файл в Интернете, не блокируя ответ пользовательского интерфейса.

## <a name="advantages-of-asynchronous-monikers"></a>Преимущества асинхронных моникеров

Асинхронные моникеры можно использовать для:

- Загрузка кода и файлов без блокировки.

- Скачивание свойств в элементах управления ActiveX без блокировки.

- Получение уведомлений о ходе загрузки.

- Отслеживание хода выполнения и сведений о состоянии готовности.

- Предоставьте сведения о состоянии пользователю о ходе выполнения.

- Разрешает пользователю отменить загрузку в любое время.

## <a name="mfc-classes-for-asynchronous-monikers"></a>Классы MFC для асинхронных моникеров

[Касинкмоникерфиле](reference/casyncmonikerfile-class.md) является производным от [кмоникерфиле](reference/cmonikerfile-class.md), который, в свою очередь, является производным от [колестреамфиле](reference/colestreamfile-class.md). `COleStreamFile`Объект представляет поток данных; `CMonikerFile` объект использует `IMoniker` для получения данных, а `CAsyncMonikerFile` объект выполняет это асинхронно.

Асинхронные моникеры используются преимущественно в приложениях с поддержкой Интернета и в элементах управления ActiveX для обеспечения реагирования пользовательского интерфейса во время передачи файлов. Простым примером этого является использование [кдатапаспроперти](reference/cdatapathproperty-class.md) для предоставления асинхронных свойств для элементов управления ActiveX.

## <a name="mfc-classes-for-data-paths-in-activex-controls"></a>Классы MFC для путей к данным в элементах управления ActiveX

Классы MFC `CDataPathProperty` и [ккачеддатапаспроперти](reference/ccacheddatapathproperty-class.md) реализуют свойства элементов управления ActiveX, которые могут загружаться асинхронно. Асинхронные свойства загружаются после синхронной инициации. Асинхронные элементы управления ActiveX многократно вызывают обратный вызов для указания доступности новых данных во время длительного процесса обмена свойствами.

Класс `CDataPathProperty` является производным от `CAsyncMonikerFile`. Класс `CCachedDataPathProperty` является производным от `CDataPathProperty`. Чтобы реализовать асинхронные свойства в элементах управления ActiveX, создайте класс, производный от `CDataPathProperty` или `CCachedDataPathProperty` , и переопределите [ондатааваилабле](reference/casyncmonikerfile-class.md#ondataavailable) и другие уведомления, которые вы хотите получать.

#### <a name="to-download-a-file-using-asynchronous-monikers"></a>Загрузка файла с помощью асинхронных моникеров

1. Объявите класс, производный от [касинкмоникерфиле](reference/casyncmonikerfile-class.md).

1. Переопределите [ондатааваилабле](reference/casyncmonikerfile-class.md#ondataavailable) для вывода данных.

1. Переопределите другие функции члена, включая [OnProgress](reference/casyncmonikerfile-class.md#onprogress), [онстартбиндинг](reference/casyncmonikerfile-class.md#onstartbinding)и [онстопбиндинг](reference/casyncmonikerfile-class.md#onstopbinding).

1. Объявите экземпляр этого класса и используйте его для открытия URL-адресов.

Сведения о асинхронной загрузке в элементе управления ActiveX см. в разделе [элементы управления ActiveX в Интернете](activex-controls-on-the-internet.md).

## <a name="see-also"></a>См. также раздел

[Задачи программирования для интернет-решений MFC](mfc-internet-programming-tasks.md)<br/>
[Основные сведения о программировании Интернета MFC](mfc-internet-programming-basics.md)
