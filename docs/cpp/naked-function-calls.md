---
title: Вызовы функций Naked
ms.date: 11/04/2016
helpviewer_keywords:
- virtual device drivers
- VXD virtual device drivers
- virtual device drivers, naked function calls
- naked functions
- prolog code
- epilog code
- naked keyword [C++]
- naked keyword [C++], storage-class attribute
ms.assetid: 2a66847a-a43f-4541-a7be-c9f5f29b5fdb
ms.openlocfilehash: 9b49d34d7276d3c9260488f23d1821b9708d2481
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227326"
---
# <a name="naked-function-calls"></a>Вызовы функций Naked

**Блок, относящийся только к системам Microsoft**

Функции, объявленные с **`naked`** атрибутом, создаются без кода пролога или эпилога, что позволяет создавать собственные последовательности пролога или эпилога с помощью [встроенного ассемблера](../assembler/inline/inline-assembler.md). Функции с атрибутом naked предоставляются как дополнительные функции. С их помощью можно объявить функцию, которая вызывается из другого контекста (и не C или C++), и тем самым указать другое место расположения параметров, в которых хранятся регистры. В качестве примера можно назвать такие процедуры, как обработчики прерываний. Эта возможность особенно полезна при написании драйверов виртуальных устройств (VxD).

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

- [naked](../cpp/naked-cpp.md)

- [Правила и ограничения для функций с атрибутом naked](../cpp/rules-and-limitations-for-naked-functions.md)

- [Рекомендации по написанию кода пролога или эпилога](../cpp/considerations-for-writing-prolog-epilog-code.md)

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Соглашения о вызовах](../cpp/calling-conventions.md)
