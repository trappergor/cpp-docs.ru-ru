---
title: Класс CComAutoCriticalSection
ms.date: 11/04/2016
f1_keywords:
- CComAutoCriticalSection
- ATLCORE/ATL::CComAutoCriticalSection
- ATLCORE/ATL::CComAutoCriticalSection::CComAutoCriticalSection
helpviewer_keywords:
- CComAutoCriticalSection class
ms.assetid: 491a9d90-3398-4f90-88f5-fd2172a46b30
ms.openlocfilehash: 613440eceb71f0277f4cc5de2af89fe263772797
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57301614"
---
# <a name="ccomautocriticalsection-class"></a>Класс CComAutoCriticalSection

`CComAutoCriticalSection` Предоставляет методы для получения и освобождения владения объект критической секции.

## <a name="syntax"></a>Синтаксис

```
class CComAutoCriticalSection : public CComCriticalSection
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[CComAutoCriticalSection::CComAutoCriticalSection](#ccomautocriticalsection)|Конструктор.|
|[CComAutoCriticalSection:: ~ CComAutoCriticalSection](#dtor)|Деструктор|

## <a name="remarks"></a>Примечания

`CComAutoCriticalSection` Аналогично класс [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md), за исключением `CComAutoCriticalSection` автоматически инициализирует объект критической секции в конструкторе.

Как правило, используется `CComAutoCriticalSection` через `typedef` имя [AutoCriticalSection](ccommultithreadmodel-class.md#autocriticalsection). Это имя ссылается на `CComAutoCriticalSection` при [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) используется.

`Init` И `Term` методы из [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) недоступны при использовании этого класса.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)

`CComAutoCriticalSection`

## <a name="requirements"></a>Требования

**Заголовок:** файле atlcore.h

##  <a name="ccomautocriticalsection"></a>  CComAutoCriticalSection::CComAutoCriticalSection

Конструктор.

```
CComAutoCriticalSection();
```

### <a name="remarks"></a>Примечания

Вызывает функцию Win32 [InitializeCriticalSection](/windows/desktop/api/synchapi/nf-synchapi-initializecriticalsection), который инициализирует объект критической секции.

##  <a name="dtor"></a>  CComAutoCriticalSection:: ~ CComAutoCriticalSection

Деструктор

```
~CComAutoCriticalSection() throw();
```

### <a name="remarks"></a>Примечания

Деструктор вызывает [DeleteCriticalSection](/windows/desktop/api/synchapi/nf-synchapi-deletecriticalsection), который освобождает все системные ресурсы, используемые объектом критический раздел.

## <a name="see-also"></a>См. также

[Класс CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)<br/>
[Класс CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)
