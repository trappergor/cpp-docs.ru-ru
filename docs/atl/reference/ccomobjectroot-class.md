---
title: Класс CComObjectRoot
ms.date: 11/04/2016
f1_keywords:
- CComObjectRoot
- atlcom/ATL::CComObjectRoot
helpviewer_keywords:
- CComObjectRoot class
ms.assetid: f8797c38-6e73-4f67-85c2-71654cffa8eb
ms.openlocfilehash: 9a9ffa1813fb15297d209894050b6bcce6802df2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62259369"
---
# <a name="ccomobjectroot-class"></a>Класс CComObjectRoot

Это определение типа из [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) шаблонизируется потоковая модель сервера по умолчанию.

## <a name="syntax"></a>Синтаксис

```
typedef CComObjectRootEx<CComObjectThreadModel> CComObjectRoot;
```

## <a name="remarks"></a>Примечания

`CComObjectRoot` — `typedef` из [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) создания шаблона по умолчанию потоковая модель сервера. Таким образом [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) будет сослаться на любую [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) или [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md).

`CComObjectRootEx` обрабатывает объект управления счетчиками ссылок для объектов неагрегированные и объединены. Он содержит счетчик ссылок объекта, если объект не выполняется статистическая обработка и содержит указатель на внешняя Неизвестная строка, если объект выполняется статистическая обработка. Для агрегированных объектов `CComObjectRootEx` методы могут использоваться для обработки ошибки внутреннего объекта для создания, а также для защиты от удаления при выходе внутренние интерфейсы внешний объект или внутренний объект удаляется.

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="see-also"></a>См. также

[Класс CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)<br/>
[Класс CComAggObject](../../atl/reference/ccomaggobject-class.md)<br/>
[Класс CComObject](../../atl/reference/ccomobject-class.md)<br/>
[Класс CComPolyObject](../../atl/reference/ccompolyobject-class.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
