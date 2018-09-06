---
title: Класс CComObjectRoot | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComObjectRoot
- atlcom/ATL::CComObjectRoot
dev_langs:
- C++
helpviewer_keywords:
- CComObjectRoot class
ms.assetid: f8797c38-6e73-4f67-85c2-71654cffa8eb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 93d30c1af67159c04546076a07c78fbaec9cbb91
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43762323"
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

[Класс CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)   
[Класс CComAggObject](../../atl/reference/ccomaggobject-class.md)   
[Класс CComObject](../../atl/reference/ccomobject-class.md)   
[Класс CComPolyObject](../../atl/reference/ccompolyobject-class.md)   
[Общие сведения о классе](../../atl/atl-class-overview.md)
