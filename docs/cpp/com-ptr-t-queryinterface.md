---
title: _com_ptr_t::QueryInterface
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::QueryInterface
- _com_ptr_t.QueryInterface
helpviewer_keywords:
- QueryInterface method [C++]
ms.assetid: d03292f1-6b02-40db-9756-8b0837a97319
ms.openlocfilehash: 42953c92e4cf31b5ccd02dd51811fc1fdeedbcaf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50543836"
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