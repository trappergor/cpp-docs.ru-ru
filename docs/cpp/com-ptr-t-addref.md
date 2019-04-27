---
title: _com_ptr_t::AddRef
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::AddRef
helpviewer_keywords:
- AddRef method [C++], interface pointers
ms.assetid: c104dac3-aad3-40bb-a298-75c6cd0e63a2
ms.openlocfilehash: 7408b5c174f76673b56caffd56aaa87895bd08d4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62154946"
---
# <a name="comptrtaddref"></a>_com_ptr_t::AddRef

**Блок, относящийся только к системам Microsoft**

Вызовы `AddRef` функцию-член `IUnknown` на инкапсулированный указатель на интерфейс.

## <a name="syntax"></a>Синтаксис

```
void AddRef( );
```

## <a name="remarks"></a>Примечания

Вызовы `IUnknown::AddRef` на инкапсулированный указатель на интерфейс, вызов `E_POINTER` ошибка, если указатель имеет значение NULL.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Класс _com_ptr_t](../cpp/com-ptr-t-class.md)