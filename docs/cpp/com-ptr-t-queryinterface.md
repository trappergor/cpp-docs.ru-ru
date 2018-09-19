---
title: _com_ptr_t::QueryInterface | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::QueryInterface
- _com_ptr_t.QueryInterface
dev_langs:
- C++
helpviewer_keywords:
- QueryInterface method [C++]
ms.assetid: d03292f1-6b02-40db-9756-8b0837a97319
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e0add1d8f3fc73f78cee3e10642d7b5a12968a6a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46106878"
---
# <a name="comptrtqueryinterface"></a>_com_ptr_t::QueryInterface

**Блок, относящийся только к системам Microsoft**

Вызовы **QueryInterface** функцию-член `IUnknown` на инкапсулированный указатель на интерфейс.

## <a name="syntax"></a>Синтаксис

```
template<typename _InterfaceType> HRESULT QueryInterface (
   const IID& iid,
   _InterfaceType*& p
) throw ( );
template<typename _InterfaceType> HRESULT QueryInterface (
   const IID& iid,
   _InterfaceType** p
) throw( );
```

#### <a name="parameters"></a>Параметры

*IID*<br/>
`IID` из указателя на интерфейс.

*p*<br/>
Необработанный указатель на интерфейс.

## <a name="remarks"></a>Примечания

Вызовы `IUnknown::QueryInterface` на инкапсулированный указатель на интерфейс с указанным `IID` и возвращает результирующее необработанный указатель на интерфейс в *p*. Эта процедура возвращает значение HRESULT, указывающее успех или неудачу.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Класс _com_ptr_t](../cpp/com-ptr-t-class.md)