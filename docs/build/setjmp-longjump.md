---
title: setjmp longjump
ms.date: 11/04/2016
ms.assetid: b0e21902-095d-4198-8f9a-b6326525721a
ms.openlocfilehash: 765cef3f02bed09bed0278aaeecdcdbd55d86b67
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50427902"
---
# <a name="setjmplongjump"></a>setjmp/longjump

При включении setjmpex.h или setjmp.h, все вызовы [setjmp](../c-runtime-library/reference/setjmp.md) или [longjmp](../c-runtime-library/reference/longjmp.md) приведет к очистки, которое вызывает деструкторы и наконец вызывает.  В отличие от x86, включая setjmp.h результаты предложения finally и деструкторы не вызываются.

Вызов `setjmp` сохраняется текущего указателя стека, неизменяемые регистры и регистры MxCsr.  Вызовы `longjmp` возврат к последнему `setjmp` вызова сайта и сброса указателя стека, неизменяемые регистры и MxCsr регистрирует, в состояние, сохраненное с самой последней `setjmp` вызова.

## <a name="see-also"></a>См. также

[Соглашение о вызовах](../build/calling-convention.md)