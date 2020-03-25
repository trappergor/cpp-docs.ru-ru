---
title: _com_ptr_t::Release
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t.Release
- _com_ptr_t::Release
helpviewer_keywords:
- Release method [C++]
ms.assetid: db448b34-0efa-4f02-b701-ad1ca3ae6ca5
ms.openlocfilehash: f455e855e782a939e79898ee46e445f65d25d37a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80170596"
---
# <a name="_com_ptr_trelease"></a>_com_ptr_t::Release

**Блок, относящийся только к системам Microsoft**

Вызывает функцию члена **выпуска** `IUnknown` для указателя инкапсулированного интерфейса.

## <a name="syntax"></a>Синтаксис

```
void Release( );
```

## <a name="remarks"></a>Remarks

Вызывает `IUnknown::Release` в инкапсулированном указателе интерфейса, вызывая ошибку `E_POINTER`, если этот указатель интерфейса имеет значение NULL.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[Класс _com_ptr_t](../cpp/com-ptr-t-class.md)
