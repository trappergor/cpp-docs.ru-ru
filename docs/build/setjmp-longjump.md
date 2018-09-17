---
title: setjmp longjump | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: b0e21902-095d-4198-8f9a-b6326525721a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f53160a5deeb3ea0db111fc0aae7429b19b7cc86
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45703278"
---
# <a name="setjmplongjump"></a>setjmp/longjump

При включении setjmpex.h или setjmp.h, все вызовы [setjmp](../c-runtime-library/reference/setjmp.md) или [longjmp](../c-runtime-library/reference/longjmp.md) приведет к очистки, которое вызывает деструкторы и наконец вызывает.  В отличие от x86, включая setjmp.h результаты предложения finally и деструкторы не вызываются.

Вызов `setjmp` сохраняется текущего указателя стека, неизменяемые регистры и регистры MxCsr.  Вызовы `longjmp` возврат к последнему `setjmp` вызова сайта и сброса указателя стека, неизменяемые регистры и MxCsr регистрирует, в состояние, сохраненное с самой последней `setjmp` вызова.

## <a name="see-also"></a>См. также

[Соглашение о вызовах](../build/calling-convention.md)