---
title: "Вызовы функций naked | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
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
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: dcf93756bf4d10feb63238a1ecf3b6d3f8b340f6
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="naked-function-calls"></a>Вызовы функций Naked
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 Функции, объявленные с `naked` атрибут создаются без кода пролога и эпилога, что позволяет написать собственные последовательности пролога и эпилога [встроенный Ассемблер](../assembler/inline/inline-assembler.md). Возможности с атрибутом naked предоставляются как дополнительные возможности. С их помощью можно объявить функцию, которая вызывается из другого контекста (и не C или C++), и тем самым указать другое место расположения параметров, в которых хранятся регистры. В качестве примера можно назвать такие процедуры, как обработчики прерываний. Эта функция особенно полезна при написании драйверов виртуальных устройств (VxD).  
  
## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения  
  
-   [naked](../cpp/naked-cpp.md)  
  
-   [Правила и ограничения для функций с атрибутом naked](../cpp/rules-and-limitations-for-naked-functions.md)  
  
-   [Considerations for Writing Prolog/Epilog Code](../cpp/considerations-for-writing-prolog-epilog-code.md) (Особенности написания кода для пролога и эпилога)  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Соглашения о вызовах](../cpp/calling-conventions.md)
