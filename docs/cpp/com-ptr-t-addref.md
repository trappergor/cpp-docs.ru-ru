---
title: _com_ptr_t::AddRef
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::AddRef
helpviewer_keywords:
- AddRef method [C++], interface pointers
ms.assetid: c104dac3-aad3-40bb-a298-75c6cd0e63a2
ms.openlocfilehash: 51182b461aeac83c12bb18a573a49b2d4347a190
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189937"
---
# <a name="_com_ptr_taddref"></a>_com_ptr_t::AddRef

**Блок, относящийся только к системам Microsoft**

Вызывает функцию члена `AddRef` `IUnknown` в инкапсулированном указателе интерфейса.

## <a name="syntax"></a>Синтаксис

```
void AddRef( );
```

## <a name="remarks"></a>Remarks

Вызывает `IUnknown::AddRef` в инкапсулированном указателе интерфейса, вызывая ошибку `E_POINTER`, если указатель имеет значение NULL.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[Класс _com_ptr_t](../cpp/com-ptr-t-class.md)
