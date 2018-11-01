---
title: _com_ptr_t::GetInterfacePtr
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::GetInterfacePtr
helpviewer_keywords:
- GetInterfacePtr method [C++]
ms.assetid: 55e3e2c7-c939-48b5-a905-4b9cbefeea7e
ms.openlocfilehash: 6746cc97696968ca59c2771d79573bd71d86df62
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50432487"
---
# <a name="comptrtgetinterfaceptr"></a>_com_ptr_t::GetInterfacePtr

**Блок, относящийся только к системам Microsoft**

Возвращает инкапсулированный указатель на интерфейс.

## <a name="syntax"></a>Синтаксис

```
Interface* GetInterfacePtr( ) const throw( ); 
Interface*& GetInterfacePtr() throw();
```

## <a name="remarks"></a>Примечания

Возвращает инкапсулированный указатель на интерфейс, который может быть равно NULL.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Класс _com_ptr_t](../cpp/com-ptr-t-class.md)