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
ms.openlocfilehash: 14bc64314cf64e7d13c076c314419e3d636432d7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80177941"
---
# <a name="naked-function-calls"></a>Вызовы функций Naked

**Блок, относящийся только к системам Microsoft**

Функции, объявленные с атрибутом **naked** , создаются без кода пролога или эпилога, что позволяет создавать собственные последовательности пролога или эпилога с помощью [встроенного ассемблера](../assembler/inline/inline-assembler.md). Функции с атрибутом naked предоставляются как дополнительные функции. С их помощью можно объявить функцию, которая вызывается из другого контекста (и не C или C++), и тем самым указать другое место расположения параметров, в которых хранятся регистры. В качестве примера можно назвать такие процедуры, как обработчики прерываний. Эта возможность особенно полезна при написании драйверов виртуальных устройств (VxD).

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

- [naked](../cpp/naked-cpp.md)

- [Правила и ограничения для функций с атрибутом naked](../cpp/rules-and-limitations-for-naked-functions.md)

- [Considerations for Writing Prolog/Epilog Code](../cpp/considerations-for-writing-prolog-epilog-code.md) (Особенности написания кода для пролога и эпилога)

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[Соглашения о вызовах](../cpp/calling-conventions.md)
