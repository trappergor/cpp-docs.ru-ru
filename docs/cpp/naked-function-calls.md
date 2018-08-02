---
title: Вызовы функций naked | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e395bcb32858bc63b3e848f20a7d794156876e26
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2018
ms.locfileid: "39402033"
---
# <a name="naked-function-calls"></a>Вызовы функций Naked
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 Функции, объявленные с **с атрибутом naked** атрибут, создаются без кода пролога и эпилога, позволяя создавать свои собственные последовательности пролога и эпилога, используя [встроенный Ассемблер](../assembler/inline/inline-assembler.md). Возможности с атрибутом naked предоставляются как дополнительные возможности. С их помощью можно объявить функцию, которая вызывается из другого контекста (и не C или C++), и тем самым указать другое место расположения параметров, в которых хранятся регистры. В качестве примера можно назвать такие процедуры, как обработчики прерываний. Эта возможность особенно полезна при написании драйверов виртуальных устройств (VxD).  
  
## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения  
  
-   [naked](../cpp/naked-cpp.md)  
  
-   [Правила и ограничения для функций с атрибутом naked](../cpp/rules-and-limitations-for-naked-functions.md)  
  
-   [Considerations for Writing Prolog/Epilog Code](../cpp/considerations-for-writing-prolog-epilog-code.md) (Особенности написания кода для пролога и эпилога)  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Соглашения о вызовах](../cpp/calling-conventions.md)