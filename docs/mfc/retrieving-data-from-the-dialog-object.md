---
title: Извлечение данных из объекта диалогового окна
ms.date: 11/04/2016
helpviewer_keywords:
- dialog boxes [MFC], retrieving user data
- dialog box data [MFC]
- data [MFC], retrieving
- GetDlgItemText method [MFC]
- SetDlgItemText method [MFC]
- SetWindowText method [MFC]
- dialog box data [MFC], retrieving
- retrieving data [MFC]
- user input [MFC], retrieving from MFC dialog boxes
- capturing user input [MFC]
- dialog box controls [MFC], initializing values
- DDX (dialog data exchange) [MFC]
- MFC dialog boxes [MFC], retrieving user input
- data retrieval [MFC], dialog boxes
- data [MFC], dialog boxes
- DDX (dialog data exchange) [MFC], about DDX
- DDX (dialog data exchange) [MFC], retrieving data from Dialog object
- GetWindowText method [MFC]
ms.assetid: bdca2b61-6b53-4c2e-b426-8712c7a38ec0
ms.openlocfilehash: 903d76a1e672d05a3c093e528f7153562df8e3e5
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685567"
---
# <a name="retrieving-data-from-the-dialog-object"></a>Извлечение данных из объекта диалогового окна

Платформа предоставляет простой способ инициализации значений элементов управления в диалоговом окне и получения значений из элементов управления. Более трудоемкий подход, выполняемый вручную, заключается в вызове таких функций, как `SetDlgItemText` и `GetDlgItemText` класса `CWnd`, которые применяются к окнам управления. С помощью этих функций вы получаете доступ к каждому элементу управления по отдельности, чтобы задать или получить его значение, вызывая такие функции, как `SetWindowText` и `GetWindowText`. Подход платформы автоматизирует инициализацию и извлечение.

Обмен данными диалоговых окон (DDX) позволяет упростить обмен данными между элементами управления в диалоговом окне и переменными-членами в объекте диалогового окна. Exchange работает обоими способами. Чтобы инициализировать элементы управления в диалоговом окне, можно задать значения элементов данных в объекте диалогового окна, и платформа будет переносить значения в элементы управления перед отображением диалогового окна. Затем можно в любое время обновить элементы данных диалогового окна данными, введенными пользователем. На этом этапе можно использовать данные, ссылаясь на переменные члена данных.

Можно также расположить значения элементов управления диалогового окна, которые будут автоматически проверяться с помощью проверки данных диалогового окна (DDV).

DDX и DDV более подробно описаны при [обмене и проверке данных диалоговых окон](../mfc/dialog-data-exchange-and-validation.md).

Для модального диалогового окна можно получить любые данные, введенные пользователем, когда `DoModal` возвращает ИДОК, но до уничтожения объекта диалогового окна. Для немодального диалогового окна можно в любое время извлечь данные из объекта диалогового окна, вызвав `UpdateData` с аргументом **true** и доступ к переменным членов класса диалогового окна. Эта тема более подробно обсуждается в разделе [Обмен и проверка данных диалоговых окон](../mfc/dialog-data-exchange-and-validation.md).

## <a name="see-also"></a>См. также

[Работа с диалоговыми окнами в MFC](../mfc/life-cycle-of-a-dialog-box.md)
