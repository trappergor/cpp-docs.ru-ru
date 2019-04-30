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
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399282"
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