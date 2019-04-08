---
title: Класс CAccessor
ms.date: 11/04/2016
f1_keywords:
- ATL.CAccessor<T>
- ATL::CAccessor
- CAccessor
- ATL::CAccessor<T>
- ATL.CAccessor
helpviewer_keywords:
- CAccessor class
ms.assetid: b2ba959f-a686-46f3-8837-176248aef748
ms.openlocfilehash: cfc91f971fc975bcdd2c8ae37d798ff2f5a1cab0
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59039206"
---
# <a name="caccessor-class"></a>Класс CAccessor

Представляет один из типов доступа.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
class CAccessor : public CAccessorBase, public T
```

### <a name="parameters"></a>Параметры

*T*<br/>
Класс записей пользователя.

## <a name="remarks"></a>Примечания

Он используется, когда запись статически привязан к источнику данных. Запись содержит буфера. Этот класс поддерживает несколько методов доступа в наборе строк.

Используйте этот тип метода доступа, если вы знаете структуру и тип базы данных.

Если ваш метод доступа содержит поля, указывающие на область памяти (такие как `BSTR` или интерфейс), должен быть освобожден, вызовите функцию-член [CAccessorRowset::FreeRecordMemory](../../data/oledb/caccessorrowset-freerecordmemory.md) до следующей запись доступна для чтения.

## <a name="requirements"></a>Требования

**Заголовок:** atldbcli.h

## <a name="see-also"></a>См. также

[Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Ссылка на шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)