---
title: Выделение и освобождение памяти для BSTR
ms.date: 11/04/2016
f1_keywords:
- bstr
helpviewer_keywords:
- BSTRs, memory allocation
- memory deallocation, string memory
- memory [C++], releasing
- memory allocation, BSTRs
- memory deallocation, BSTR memory
- strings [C++], releasing
ms.assetid: 98041e29-3442-4a02-b425-7a4a13e9cc84
ms.openlocfilehash: 5d21134b85013f9a8ae508590f1a8db0c2e7a7e4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50668576"
---
# <a name="allocating-and-releasing-memory-for-a-bstr"></a>Выделение и освобождение памяти для BSTR

При создании `BSTR`s и передавайте их между COM-объектов, необходимо соблюдать осторожность в обработке памяти, они используют, чтобы избежать утечки памяти. Когда `BSTR` остается в интерфейсе, вы должны освобождать память при всех возложенных на него. Тем не менее, если `BSTR` передает из интерфейса, получающий объект отвечает за его управление памятью.

Как правило, выделенной правила выделение и освобождение памяти для `BSTR`s, следующим образом:

- При вызове в функцию, ожидающую `BSTR` аргумент, необходимо выделить память для `BSTR` до вызова и выпустить ее позже. Пример:

   [!code-cpp[NVC_ATLMFC_Utilities#192](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_1.cpp)]

   [!code-cpp[NVC_ATLMFC_Utilities#193](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_2.cpp)]

- При вызове в функцию, возвращающую `BSTR`, необходимо освободить строку самостоятельно. Пример:

   [!code-cpp[NVC_ATLMFC_Utilities#194](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_3.cpp)]

   [!code-cpp[NVC_ATLMFC_Utilities#195](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_4.cpp)]

- При реализации функции, возвращающей `BSTR`, выделить строки, но не освободит его. Поставка функция освобождает память. Пример:

   [!code-cpp[NVC_ATLMFC_Utilities#196](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_5.cpp)]

## <a name="see-also"></a>См. также

[Строки (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[CStringT::AllocSysString](../atl-mfc-shared/reference/cstringt-class.md#allocsysstring)<br/>
[SysAllocString](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-sysallocstring)<br/>
[SysFreeString](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-sysfreestring)

