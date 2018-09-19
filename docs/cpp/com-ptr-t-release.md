---
title: _com_ptr_t::Release | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t.Release
- _com_ptr_t::Release
dev_langs:
- C++
helpviewer_keywords:
- Release method [C++]
ms.assetid: db448b34-0efa-4f02-b701-ad1ca3ae6ca5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 444f56c1a999f09a79d725173c9f0f19399ab363
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118366"
---
# <a name="comptrtrelease"></a>_com_ptr_t::Release

**Блок, относящийся только к системам Microsoft**

Вызовы **выпуска** функцию-член `IUnknown` на инкапсулированный указатель на интерфейс.

## <a name="syntax"></a>Синтаксис

```
void Release( );
```

## <a name="remarks"></a>Примечания

Вызовы `IUnknown::Release` на инкапсулированный указатель на интерфейс, вызов `E_POINTER` ошибка, если этот указатель интерфейса имеет значение NULL.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Класс _com_ptr_t](../cpp/com-ptr-t-class.md)